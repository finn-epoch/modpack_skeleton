# README.md

A modpack skeleton! If you see this text still, you should really update it!!

This skeleton is suitable for starting Thunderstore.io modpacks for the Valheim game

A modpack consists of the following:

  - A `README.md` file describing the contents of the modpack
  - An `icon.png` file the is used on the website. This should be a 256x256 px `.png` file. To obtain one, I went to [OpenAI] and used the prompt "An icon for a game modpack source code skeleton template". This was then downloaded as a `.jpg` file. I then used [ImageMagick] to convert the file via `mogrify -resize 256x256 download.jpg` and finally `mogrify -format png download.jpg`
  - A `CHANGELOG.md` file which maintains a running list of updates to the modpack. When and how to prune this is left to the modpack author.
  - Finally, a `manifest.json` file, which fully describes the modpack metadata and provides a JSON-formatted list of the mods contained in the modpack. This string requires a specific format, called the 'Dependency String' and is available for every mod available on Thunderstore.io. As you add items to this list, keep in mind the following:
    - The last item in the list should NOT have a trailing comma
    - The version number needs to be incremented for each release
    - The website_url will actually be published on Thunderstore.io; best to just point it at the repo IMO
    - To get going you'll need at least a proper name and desription


Additionally, this source tree contains a GitHub action that will publish the modpack to the Thunderstore.io site. This file is found in `.github/workflows/main.yml` and will periodically need to have version numbers incremented. This action runs on every new "Release" on GitHub; it checks out the code, zips it up correctly, and then uploads it to Thunderstore.io

Note that the action also requires the existence of a secret named `secrets.THUNDERSTORE_API_TOKEN`. The signup process at Thunderstore.io will walk you through acquiring this token. Don't be foolish and hardcode your API token in the code and then check it into a public GitHub.

[markdown]: https://daringfireball.net/projects/markdown/
[gfm]: https://github.github.com/gfm/
[guide]: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github
[OpenAI]: https://deepai.org/machine-learning-model/text2img
[ImageMagick]: https://imagemagick.org/