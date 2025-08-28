## design philosophy
### composition + traits instead of inheritance
- **[[r struct]] composition**: build bigger types by combining smaller ones
- **Trait composition**: implement multiple traits on one type for modular behavior.
- **Delegation**: forward method calls to inner fields (manual or with macros).
- **Newtype pattern**: wrap existing types for stronger typing.
- **Enums**: compose multiple possibilities into one type.