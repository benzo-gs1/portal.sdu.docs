# Loaders 🛫

This document describes loading process:

1. _main_() runs initializing **Loaders** and passing cli arguments to it.
2. **Configurations** are initializing
3. **Event Pipe** is initializing
4. **Database** is initializing
5. **Express Loader** applying middleware plugins and returning instance of _Express_ app
6. **Service Collector** importing all the services defined in a services/ folder
7. **Route Collector** recursively running through routes/ folder and collecting all the _Express_ controllers
8. **system::setup** event is fired
