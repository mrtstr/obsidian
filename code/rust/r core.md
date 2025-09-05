### core
- [[r crate]] that are even lower than [[r std]] and always included in the binary (together with [[r alloc]]) during the [[compiler#code generation]]
- first layer of the [[rust]] standard library ([[r std]])
- contains bare essentials with no dependency on the [[li heap]] and the [[system C libraries]] of the OS
- Even in `#![no_std]` environments, you’ll still pull in `core`

Examples:
- Basic [[r data type]]: [[r option]], [[r result]], `str`, [[r slicing]], [[r array]], [[r tuple]]...
- [[r trait]]: `Copy`, `Clone`, `Iterator`, [[r drop]], arithmetic traits...
- Utilities: [[r panic]]