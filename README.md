## Unixporn Poster

Small cli tool for quickly making a post to [r/unixporn](https://reddit.com/r/unixporn)

![](https://github.com/Lifesgood123/unixpornposter/blob/master/show_off.gif?raw=true)

### Installation & Setup

```shell
pip install --user unixpornposter
```

1. Create a new app at https://www.reddit.com/prefs/apps/ and get a `client_id` and `client_secret`

1. Create a file at `~/.config/unixpornposter/redditCreds` and populate it like this 

   ```python3
   {'client_id'     : 'your_client_id',
    'client_secret' : 'your_client_secret',
    'user_agent'    : 'a script',
    'username'      : 'your_username',
    'password'      : 'your_password'}
   ```

### Usage 

1. Make a rice directory

   ```
   sowmRice/
    ⮡ screenshot1.png
    ⮡ screenshot2.jpg
    ⮡ screenshot3.gif
    ⮡ details
   ```

   The details file is info for your post, inclusing the details comment information, and the title, it should look like this: 

   ```python3
   {"Wallpaper"   : ("Smoking Maid",         "https://www.pixiv.net/en/artworks/58837536"),
    "Terminal"    : ("st",                   "st.suckless.org"),
    "Colorscheme" : ("base16-unikitty-dark", "https://github.com/joshwlewis/base16-unikitty"),
    "Startpage"   : ("My Fork of ArchLabs",  "https://github.com/lifesgood123/.ArchLabs-homepage"),
    "title"       : "I can't wait to be done with this"
    "wm"          : "sowm"
    }
   ```
   
Entries can be either a `str` or a `tuple`, and both the `title` and `wm` entries must be strings, and are required. 
   
1. Run the poster

   `unixpornpost /rice/directory/here`

### Notes on command-line options

So far the only available option is `-g` . If set it will utilise the `katfetch` module to grab some basic information like your terminal, wm, shell, and distro. Whatever is in your details file takes precedent over whatever is generated by katfetch. 

###### Todo

- Create more options for the details file format
- Design logging system to ensure no duplicate post are made
- Add support for videos (this one's fairly easy)
