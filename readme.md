# Visual Code Studio Template for ESP32

### Modify the default project name called `main` and paths

1. Open `CMakeLists.txt` and replace `main` by your project name
2. Open `Makefile` and replace `main` by your project name
3. Open `.vscode/launch.json` and replace `main` by your project name (lines 11 and 19)
4. Modify the paths if wrong in the `c_cpp_properties.json` file.

```json
"IDF_TOOLS": "~/.espressif/tools",
"IDF_PATH": "~/esp/esp-idf"
```

### Commands 

#### Open external terminal from vscode to perform commands

  * using keyboard shortcut: `Ctrl+Shift+C`,
  * or pressing `F1` key and typing `Open new external terminal`


#### Configuration of the ESP32 board
```bash
idf.py menuconfig
```

#### Compile and build the executable file (`.elf` extension)
```bash
idf.py build
```

#### Identify the USB serial port (usually `/dev/ttyUSB0`)
```bash
ls /dev/ttyUSB*
```

#### Compile, build, flash
```bash
idf.py -p /dev/ttyUSB0 flash
```

#### Compile, build, flash and monitor
```bash
idf.py -p /dev/ttyUSB0 flash monitor
```

### Configure GIT for the first use

#### First GIT use (just once for all projects)
```bash
git config --global user.name "Your name" 
git config --global user.email "your email address"
```

#### Avoid typing your username and password in vscode each time
```bash
git config credential.helper store
```

### Import ESP32 Visual Code template project from GitHub

#### 1. Open a terminal where you will create the project

#### 2. Clone the `vscode_project_template` project
```bash
git clone https://github.com/fmuller-pns/vscode_project_template.git
```
#### 3. Rename the `vscode_project_template` folder
```bash
mv vscode_project_template  my_project_name
```
#### 5. Remove the GIT directory
```bash
cd my_project_name
rm -R .git
```
#### 6. Open visual studio code for the new project
```bash
cd my_project_name
code .
```
#### 7. Verify paths in the `c_cpp_properties.json` file and change them if wrong.
```json
"IDF_TOOLS": "~/.espressif/tools",
"IDF_PATH": "~/esp/esp-idf"
```
#### 8. [Not required] Change the default project name called `main` in files.
1. Open `CMakeLists.txt` and replace `main` by your project name
2. Open `Makefile` and replace `main` by your project name
3. Open `.vscode/launch.json` and replace `main` by your project name (lines 11 and 19)

### Using GITHUB with visual studio code

We consider you have:
* Configured GIT for the first use
* Imported ESP32 Visual Code template project from GitHub or create a new project

1. Open visual code studio.
2. Click on the `Source Control` icon on your left side or use `Ctrl+Shift+G` shortcut. 
3. For the first time, click on `Initialize Repository`
4. Enter a message for your first commit (ex: first commit) and click on Commit icon
5. Press `F1` and typing `git add remote`
6. *remote name* : your github repository previously created
7. *remote url* : https://github.com/xxx/your_project.git
8. *username* and *password*
9. Push to the server (master branch)

See https://code.visualstudio.com/docs/editor/versioncontrol for more details.

### Generate Doxygen documentation

1. Open external terminal from vscode, using keyboard shortcut: `Ctrl+Shift+C`, or pressing `F1` key and typing `Open new external terminal`
2. Generate HTML documentation

  * From the User interface (allow you updating the `Doxyfile` configuration file)

```bash
doxywizard
```

  * Directly from `Doxyfile` configuration file


```bash
doxygen
```
3. A new `html` folder  is created, the entry file is `index.html`

