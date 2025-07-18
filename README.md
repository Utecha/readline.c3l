# readline.c3l

This project provides bindings to the
[GNU Readline](https://tiswww.case.edu/php/chet/readline/rltop.html)
library for the [C3](https://c3-lang.org/) language.

Anything that is not a direct "extern" call is written to try and replicate
the functionality exactly as it was intended in C.

Not *everything* was included in this project. Much of the library is not really
meant to be user-facing. The overwhelming majority (theoretically the entirety)
of the actual API has been bound with some minor exceptions, such as what is
found in `readline/keymaps.h` and `readline/rltypedefs.h`.

NOTE: GNU Readline is not Windows compatible. This library is only compatible
with Unix-like operating systems.

## Usage

It's generally recommended to start a new C3 project using the provided project
system (i.e. ```c3c init my_project```.) Assuming you do so, start by cloning
this repository into your `lib` directory.

```sh
git clone https://github.com/Utecha/readline.c3l.git
```

Then, in your `project.json`, add to the dependencies list `readline.c3l`.

To use it in your project, import it using ```import readline::rl```.

Usage example for a simple REPL with history:

```c3
module myproj;
import readline::rl;
import std::io;

fn void repl()
{
    for (;;)
    {
        char *input = rl::readline(">>> ");
        if (!input) // EOF check (Ctrl-D)
        {
            io::printn(); // Close out cleanly :)
            return;
        }

        add_history(input);
        do_thing_with_input(input);
        free(input);
    }
}
```

## License

This project is governed by the GNU GPL v3 license, as is the original project.
The license for this project is found in ```LICENSE```, and the original license
for GNU Readline is found under ```LICENSE-GNU```.
