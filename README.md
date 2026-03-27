# RMPC Configuration

This is my **RMPC (Rust Music Player Client) configuration** along with the corresponding MPD setup. RMPC is a terminal-based music player client with tabs, keybindings, and visualizations.

<br>

![screenshot](https://github.com/Tschonitsch/rmpc/blob/main/screenshot.png)

---

## 🔹 Features

* **MPD Backend:** Connects to MPD running on `localhost:6600`.
* **Hot Reload:** Configuration reloads automatically.
* **Volume Control:** Step size of 5.
* **Max FPS:** 30 for UI updates.
* **Mouse Support:** Enabled for navigation.
* **Album Art:** Auto method, max size 1000x1000, centered.
* **Tabs:** Playing, Albums, Songs, Cava (visualizer), Lyrics, Find.
* **Lyrics Directory:** `~/Music`
* **Search:** Case insensitive, modes include title, album, artist, genre, filename.
* **Queue Management:** Play, Add, Delete, Save, Jump to current.

<br>

## ⚡ RMPC Keybindings

### Global

| Key | Action                 |
| --- | ---------------------- |
| `:` | Command Mode           |
| `,` | Volume Down            |
| `.` | Volume Up              |
| `p` | Play/Pause             |
| `>` | Next Track             |
| `<` | Previous Track         |
| `z` | Toggle Repeat          |
| `x` | Toggle Random          |
| `c` | Toggle Consume         |
| `v` | Toggle Single          |
| `~` | Show Help              |
| `I` | Show Current Song Info |
| `O` | Show Outputs           |
| `P` | Show Decoders          |
| `q` | Quit                   |

### Navigation

| Key             | Action       |
| --------------- | ------------ |
| `k` / `<Up>`    | Up           |
| `j` / `<Down>`  | Down         |
| `h` / `<Left>`  | Left         |
| `l` / `<Right>` | Right        |
| `a`             | Add          |
| `A`             | Add All      |
| `r`             | Rename       |
| `/`             | Enter Search |
| `<CR>`          | Confirm/Play |
| `D`             | Delete       |

### Queue

| Key     | Action          |
| ------- | --------------- |
| `<CR>`  | Play            |
| `a`     | Add to Playlist |
| `d`     | Delete          |
| `i`     | Show Info       |
| `C`     | Jump to Current |
| `<C-s>` | Save Playlist   |
| `D`     | Delete All      |

---

## 🎵 MPD Configuration

```text
music_directory    "~/Music"
playlist_directory "~/.config/mpd/playlists"
db_file            "~/.config/mpd/mpd.db"
log_file           "~/.config/mpd/mpd.log"
auto_update        "yes"
bind_to_address    "localhost"
port               "6600"

state_file         "~/.config/mpd/mpdstate"
sticker_file       "~/.config/mpd/sticker.sql"

audio_output {
    type    "alsa"
    name    "Speakers"
    mixer_type "software"
}

audio_output {
    type    "fifo"
    name    "cava"
    path    "/tmp/mpd.fifo"
    format  "44100:16:2"
}
```

* **Audio Outputs:** Supports ALSA for speakers and FIFO for Cava visualization.
* **Auto Updates:** MPD updates database automatically.

<br>



## 🔗 Resources

* [RMPC GitHub](https://github.com/mierak/rmpc)
* [MPD Official](https://www.musicpd.org/)
