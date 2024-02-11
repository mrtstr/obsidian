terminals are ways to provide input to and get output from a system

terminal session initializes and controls interactive processes

Software terminal, i.e., virtual TeleTYpe ([TTY](https://www.baeldung.com/linux/monitor-keyboard-drivers)), which is the main interface of a Linux operating system
Software pseudo-terminal, i.e., PseudoTeletYpe (PTY), which allows emulating a TTY

TTY and PTY
- TTY is an acronym for _teletype_ or _teletypewriter_. In essence, **TTYs are devices that enable typing (_type_, _typewriter_) from a distance (_tele_)**.

PTY is an acronym for _pseudo-TTY_. **The name _PTY_ stems from the fact that it behaves like a TTY but for any two endpoints**. This minor difference enables multiple PTYs to co-exist within the context of the same TTY.

A **terminal emulator**, or **terminal application**, is a [computer program](https://en.wikipedia.org/wiki/Application_software "Application software") that [emulates](https://en.wikipedia.org/wiki/Emulator "Emulator") a video [terminal](https://en.wikipedia.org/wiki/Computer_terminal#Dumb_terminals "Computer terminal") within some other display architecture. Though typically synonymous with a [shell](https://en.wikipedia.org/wiki/Command-line_interface "Command-line interface") or [text terminal](https://en.wikipedia.org/wiki/Text_terminal "Text terminal"),