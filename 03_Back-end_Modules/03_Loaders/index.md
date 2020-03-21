# Loaders 🛫

This document describes loading process:

1. _main_() runs initializing **Loaders** and passing cli arguments to it.
2. **Configurations** are initializing
3. **Event Pipe** is initializing
4. **Express Loader** applying middleware plugins and returning instance of _Express_ app
5. **Route Collector** recursively running through routes/ folder and collecting all the _Express_ controllers
