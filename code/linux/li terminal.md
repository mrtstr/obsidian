terminals are ways to provide input to and get output from a system

terminal session initializes and controls interactive processes

Software terminal, i.e., virtual TeleTYpe ([TTY](https://www.baeldung.com/linux/monitor-keyboard-drivers)), which is the main interface of a Linux operating system
Software pseudo-terminal, i.e., PseudoTeletYpe (PTY), which allows emulating a TTY

TTY and PTY
- TTY is an acronym for _teletype_ or _teletypewriter_. In essence, **TTYs are devices that enable typing (_type_, _typewriter_) from a distance (_tele_)**.

PTY is an acronym for _pseudo-TTY_. **The name _PTY_ stems from the fact that it behaves like a TTY but for any two endpoints**. This minor difference enables multiple PTYs to co-exist within the context of the same TTY.