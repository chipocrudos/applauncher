# AppLauncher

I want to share this plugin, I use [Terminator](https://terminator-gtk3.readthedocs.io/en/latest/), and every time I wanted to set up my development environment, I had to launch Terminator and execute the commands needed. In order to avoid this repetitive sequence, I decided to write a plugin that, with just one click, launches Terminator, creates divisions in it, and executes the commands needed for every project.

## Installation

1. Put files in `~/.config/terminator/plugins/`:

        mkdir -p ~/.config/terminator/plugins
        cp applauncher.py ~/.config/terminator/plugins/
        cp projects.py ~/.config/terminator/plugins/

2. Restart [Terminator](https://terminator-gtk3.readthedocs.io/en/latest/), go to `Context menu > Preferences > Plugins` and select `AppLauncher`.

## Setup

1. Edit `~/.config/terminator/plugins/projects.py`, example:

        :::python
        EDITOR = "gedit"
        
        PROJECTS = {"Project 1": {"split": "vert",
                                  "terminal1": {"split": "horiz",
                                                "terminal1": {"commands": ["dir"],
                                                              },
                                                "terminal2": {"commands": ["ls"],
                                                              }
                                                },
                                  "terminal2": {"commands": ["dir"], 
                                                },
                                  },
                    "Project 2": {"enabled": False,
                                  "split": "vert",
                                  "terminal1": {"split": "horiz",
                                                "terminal1": {"commands": ["command 1",
                                                                           "command 2",
                                                                           "command 3"],
                                                              },
                                                "terminal2": {"commands": ["command"],
                                                              }
                                                },
                                  "terminal2": {"split": "horiz",
                                                "terminal1": {"commands": ["command"],
                                                              },
                                                "terminal2": {"commands": ["command"],
                                                              }
                                                },
                                  },
                    "Project 3": {"enabled": True, commands": ["history", ] }
                    }
        
        

2. Restart Terminator.

## Use

* Go to `Context menu > AppLauncher`, and select your project.

## Autor

* Guido Castillo Gómez gcasgo@gmail.com

* Guillermo Moguel Mandujano guillom4@gmail.com (Updated)

## License

The plugin is licensed as GPLv2 only.



