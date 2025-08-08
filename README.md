# Textual Setup Screen

This is a generic setup screen for textual apps.

---

## Video Example
https://github.com/user-attachments/assets/2dcdb0b1-919c-497b-a874-923b582feb3e

---

## Code Example

```python
from textual_setup_screen import setup_screen

from shoal import game_runner
from shoal.main_app import app

def push_install_h1_screen():
    if not os.path.isfile(get_h1_mod_exec_path()):
        download_h1_mod_screen = setup_screen.SetupScreen(
            step_text_to_step_functions={
                "Downloading Aurora's H1-Mod...": download_h1_mod
            },
            finished_all_steps_function=game_runner.run_game,
            widgets_to_refresh_on_screen_pop=[],
            screen_label_text="Aurora's H1-Mod Setup:"
        )
        app.push_screen(download_h1_mod_screen)
    else:
        game_runner.run_game()
```

---

## Adding to Project Example
```bash
uv add git+https://github.com/Mythical-Github/textual-setup-screen
```
