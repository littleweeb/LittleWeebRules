# LittleWeebRules
Here are some hard coded rules for anime searching used by https://github.com/EldinZenderink/LittleWeeb.

It's somewhat similar to https://github.com/erengy/anime-relations/, but it will cover anime's such as Steins;Gate & Steins;Gate 0, where it's technically impossible to differentiate between those two, while keeping in mind that some anime's are released with slightly different episode names (or titles within episode names) where there is never a 100% exact title match using titles used by anime databases such as kitsu, mal, anilist, etc. 

This will grow hopefully as more users start using littleweeb.

You can contribute to this list using the following rules:

1. Make sure that the anime hasn't been covered by https://github.com/erengy/anime-relations/
2. Make sure that the anime will not be covered by https://github.com/erengy/anime-relations/
    - anime-relations is used when animes with different season titles are released by subgroups as ONE anime (boku no hero by horriblesubs for example, where they continue on numbering without differentiating different seasons) (you can read more about it on https://github.com/erengy/anime-relations/)
 
3. Use the search fied on https://nibl.co.uk/bots.php to find all the possible episode names used by that exact anime that your looking for (no alternatives like other seasons, ova's, movies, etc.).

4. Use the following url `https://kitsu.io/api/edge/anime?filter[text]={animetitle}&fields[anime]=id,canonicalTitle` where {animetitle} should be replaced with the title that you want to add.

5. Note down the value of canonicalTitle & id of the anime that you want to add.

6. Use the following syntax (it's not case sensitive!) (remove the whole {} containing the tag name):

        ~
        # {canonicalTitle}
        * {id}
        + `{must have identicator within possible episode titles}`,`{another indenticator}`
        - `{part (word) of episode title possibly used with other versions of the anime}`,`{another part}`
        $ `{part of title it must not contain}`,`{another part}`
    
7. For example:

        ~
        # Steins;Gate 0
        * 10788
        + `0`
        - `Steins `, `Gate`
        $
    
This means that in case littleweeb finds an episode for `Steins;Gate 0` with the title `[HorribleSubs] Steins Gate 0 - 01 [1080p].mkv`, it will show this episode because it contains `0`.

Littleweeb is not that smart and will also find episodes when searching for `Steins;Gate 0` with names such as `	[deanzel] Steins;Gate - 14 [BD 1080p Hi10p Dual Audio FLAC][9ea26b1d].mkv`, but this one won't be shown when viewing `Steins;Gate 0` because it does NOT have ` 0 ` within it's name. 

That's how it works!


