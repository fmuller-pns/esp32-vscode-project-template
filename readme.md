# Visual Code Studio Template for ESP32

## Getting Started

Thank you ! you just have cloned the `esp32-vscode-project-template` project.
```bash
git clone https://github.com/fmuller-pns/esp32-vscode-project-template.git
```

#### 1. Rename the `vscode_project_template` folder
```bash
mv esp32-vscode-project-template <my_project_name>
```
#### 2. Go to the project directory
```bash
cd <my_project_name>
```
#### 3. Remove the GIT directory
```bash
rm -fR .git
```
#### 4. Open visual studio code for the new project
```bash
code .
```
#### 5. Verify paths in the `c_cpp_properties.json` file and change them if wrong.
```json
"IDF_TOOLS": "~/.espressif/tools",
"IDF_PATH": "~/esp/esp-idf"
```
#### 6. [Not required] Change the default project name called `main` in files.
This step renames the executable file. By default, the executable file is `main.elf`.
1. Open `CMakeLists.txt` and replace `main` by <my_project_name>
2. Open `Makefile` and replace `main` by <my_project_name>
3. Open `.vscode/launch.json` and replace `main` by <my_project_name> (lines 11 and 19)

#### 7. Open an terminal from vscode to perform commands
Choose an externant or internal terminal.

##### Open integrated terminal from vscode

  * using keyboard shortcut: `Ctrl+Shift+`<sup>2</sup>
  * or pressing `F1` key and typing `integrated`

##### Open external terminal from vscode

  * using keyboard shortcut: `Ctrl+Shift+C`
  * or pressing `F1` key and typing `external`

#### 8. Identify the USB serial port (usually `/dev/ttyUSB0`)
```bash
ls /dev/ttyUSB*
```
<span style="color:yellow">/dev/ttyUSB0</span>

#### 9. Building, flashing and running project
The serial port is `/dev/ttyUSB0` identified above.

```bash
idf.py -p /dev/ttyUSB0 flash monitor
```

##### Push the button on the ESP32 board when connecting

```bash
Serial port /dev/ttyUSB0
Connecting........_____....._
Detecting chip type... ESP32
Chip is ESP32-PICO-D4 (revision 1)
```

##### Flashing and monitoring
The message "`Hello ESP32 !`" appears.
```bash
...
W (290) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
I (300) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
Hello ESP32 !
```

To exit monitoring, typing `Ctrl+AltGr+]`

## Useful Commands 

#### Open external terminal from vscode to perform commands

  * using keyboard shortcut: `Ctrl+Shift+C`
  * or pressing `F1` key and typing `external`

#### Open integrated terminal from vscode to perform commands

  * using keyboard shortcut: `Ctrl+Shift+`<sup>2</sup>
  * or pressing `F1` key and typing `integrated`

#### Clean project
```bash
idf.py fullclean
```

#### Configuration of the ESP32 board (only in external terminal)
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
To exit monitoring, typing `Ctrl+AltGr+]`

## Configure GIT for your new project

#### Go to your new project folder
```bash
cd <project_name>
```
#### Configure name and email address
```bash
git config --global user.name "your name" 
git config --global user.email "your email address"
```
#### Avoid typing your username and password in vscode each time
This is useful when connecting your GIT to GitHub.
```bash
git config credential.helper store
```

## Using GITHUB with visual studio code

We consider you have followed the sections above:
* Getting Started
* Configure GIT for your new project

Now, how to communicate with GitHub ?

1. Open visual code studio.
2. Click on the `Source Control` icon on your left side or use `Ctrl+Shift+G` shortcut. 
3. For the first time, click on `Initialize Repository` button
4. Enter a message for your first commit (ex: first commit) and click on Commit icon
5. Press `F1` and typing `git add remote` and entering :
   * *remote name* : your github repository previously created
   * *remote url* : https://github.com/xxx/your_project.git
   * *username* and *password*
6. Push to the GitHub server (master branch)

See https://code.visualstudio.com/docs/editor/versioncontrol for more details.

## Generate Doxygen documentation

1. Open external terminal from vscode, using keyboard shortcut: `Ctrl+Shift+C`, or pressing `F1` key and typing `external`
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

