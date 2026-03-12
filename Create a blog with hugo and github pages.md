
1. Install hugo. Go [here](https://github.com/gohugoio/hugo/releases/tag/v0.157.0) and from the assets section download suitable binary for your system. Don't download package starting with `hugo_extended`. For my system I downloaded `hugo_0.157.0_linux-arm64.deb`. Install this.

2. We'll create 2 repositories on github. The idea is, we will use one repository to store our blog code and other repository to deploy our code (from github pages).

3. Create an empty repository named **blog**.

4. Create another repository called `your-github-username.github.io`. Create an empty README.md file for this repository.

5. Now, clone the **blog** repository locally. `cd` into the new **blog** directory and run `hugo new site name-of-your-site`. 

6. `cd` into `name-of-your-site` then `cd` into `themes` and run `git clone <theme-git-url>`.

7. Come back up one directory by `cd ../`.  Now you're in `name-of-your-site` directory. Now edit `hugo.toml` file

```
baseURL = 'https://atulvishw240.github.io/'
theme = 'LoveIt'
```

8. Now run `hugo server` from the `name-of-your-site` to preview our site locally.

9. To create a new posts
