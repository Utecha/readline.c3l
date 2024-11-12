# GNU readline

This repo contains bindings to the GNU 'readline' library (written in C) for the C3 language. Anything that is not a direct extern call is written to try and replicate
the functionality exactly as it was intended in C.

#### NOTE

This project is a work in progress. So far I theoretically have the entire library bound, however there is no guarantee everything works as intended without testing it.

In effect, the bindings are largely untested (mostly the macros), however I have personally used the 'readline' and 'add_history' functions on several occasions before I decided
to write these bindings.

One thing I would like to do is improve the UX of the library. For example, 'readline' takes in a [char *] and outputs a [char *]. Ideally I'd like to wrap that in some way to
return either a String, or ZString as they are generally nicer to work with.
