# NeverSink-EconomyUpdated-SC-Filter

This is the SOFTCORE auto-generated version of my filter. It's updated every 4 hours, using a cloud-hosted dataprocessing pipeline.

--------------------------

**BARE MINIMUM YOU SHOULD KNOW**

--------------------------

Be sure to read the readme: https://github.com/NeverSinkDev/NeverSink-Filter first.

This filter is usually much more finetuned, than the stable version. However, as the name suggests, while the stable version is tripple checked to work well, there's a tiny chance for anomalies here.

If you're an experienced POE player, want to have an edge on the market or just want to GIT PULL your updates every day, this repository is for you.

--------------------------

**INSTALLATION:**

--------------------------

1) Download the archive.

2) Extract the files using WinRar/7zip or a similar tool.

3) Paste the .filter files into the following folder: *%userprofile%/Documents/My Games/Path of Exile* . If you want to use a specific style, paste the files from one of the (STYLE) folders instead. The folders have to be in the root directory, not a subdirectory of the "Path of Exile" folder.

4) INGAME: Escape -> Options -> UI -> Scroll down -> Select one of the filters from the dropdown box.

5) Done. Enjoy.

If you want to edit the filter in a text-editor I've create a *[notepad++](https://github.com/NeverSinkDev/NotepadPP-PoE-Filter-Markup-Language)* and a *[visual studio code](https://github.com/NeverSinkDev/VS-Code-PoE-Filter-Markup-Extension)* filter highlight language!

--------------------------

**SUPPORT:**

--------------------------

The filter itself will always be free, including updates. There will never be any premium/donator versions or options! 

If you want to support the the development of the filter and/or filterblade or just show your appreciation feel free to **[buy me a beer / donate](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=6J3S7PBNDQGY2)**. I also have a **[Patreon](https://www.patreon.com/user/overview?u=8230879)** account.

Your support is appreciated. Thank you!

--------------------------

**HOW IS THIS CREATED?:**

--------------------------

The function is currently hosted in Microsoft Azure and runs every 4 hours, triggered by a logic app. 

This is the current workflow:

- Runs the compiled version of the following C# code: https://github.com/NeverSinkDev/FilterPolishZ
- Retrieves the latest economy data from www.poe.ninja for the appropriate league
- Retrieves the latest seed filter from https://github.com/NeverSinkDev/NeverSink-Filter/blob/master/ADDITIONAL-FILES/SeedFilter/NeverSink's%20filter%20-%20SEED%20(SeedFilter)%20.filter
- Retrieves the latest aspect files from https://github.com/NeverSinkDev/Filter-ItemEconomyAspects
- Retrieves the latest style information from https://github.com/NeverSinkDev/NeverSink-Filter/tree/master/ADDITIONAL-FILES/StyleSheets
- It then turns the filter into an internal representation
- Tierlists are extracted.
- The league-type and current economy status (such as exalted orb price) are considered
- Poe.ninja economy information is augmented with aspects and enrichment procedures - custom algorithms, designed to quantify game knowledge. For instance, this helps fighting price fixers, treats pricing anomalies, provides additional information, if an item only drops in a certain league etc.
- Based on all the steps above, each unique, divination card, oil, scarab, shaper, elder, unique map, prophecy, fossil, incubators and other tiers are evaluated. Each item category has it's own rules, threshholds, safety checks and algorithms.
- Items that have sufficiently changed are moved to a different tier.
- The filter structure is then cleaned up, adjusted, tested and finetuned.
- The filter is then reconstructed, using different variations, based on the style and strictness combination.
- The created filters are uploaded into the appropriate repository.

If you want to understand or contribute the mechanics, behind the tiering algorithm, you can find the relevant code here in the following repository: https://github.com/NeverSinkDev/FilterPolishZ

