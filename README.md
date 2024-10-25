### BUILD

```bash
cmake -S . -B build/
cmake --build build/ -j
```

**NOTICE:** this is okay if configuration step will take a long time first time
            because I used `FetchContent` in *CMakeLists.txt* to download deps.

