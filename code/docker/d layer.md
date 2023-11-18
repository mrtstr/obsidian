## [[d layer]]
- A [[docker]] build consists of a series of ordered build instructions
- Each instruction in a [[dockerfile]] roughly translates to an [[d image]] [[d layer]]
- If a [[d layer]] of an image is unchanged, then the builder picks it up from the build cache
- If a [[d layer]] has changed since the last build, that layer, and all layers that follow, must be rebuilt.

![[layers 1.png]]
→ things that take a long time to build and are rarely changing should be on top

# anki

START
Basic
why does the order of commands in a [[dockerfile]] matter plus underlaying concept
Back: 
## [[d layer]]
- A [[docker]] build consists of a series of ordered build instructions
- Each instruction in a [[dockerfile]] roughly translates to an [[d image]] [[d layer]]
- If a [[d layer]] of an image is unchanged, then the builder picks it up from the build cache
- If a [[d layer]] has changed since the last build, that layer, and all layers that follow, must be rebuilt.
![[layers 2.png]]
→ things that take a long time to build and are rarely changing should be on top
Tags: code docker
<!--ID: 1700318860083-->
END