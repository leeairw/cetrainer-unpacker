CheatEngine Trainer Unpacker
============================

This program extracts and decrypts CheatEngine's `.CETRAINER` files packed inside arbitrary trainer executables.

Written in [Python 3.7](https://www.python.org/downloads/).

## Download

Clone the repository from: [https://github.com/AlexAltea/cetrainer-unpacker](https://github.com/AlexAltea/cetrainer-unpacker).

## Usage

Run the following command with administrator privileges:

```
extract.py path/to/trainer.exe [path/to/trainer.xml]
```

Note that the second argument is optional and defaults to: `path/to/trainer.exe.xml`.


## Files

### `extract_dynamic.py`

Extracts the `*.CETRAINER` file via binary instrumentation with [Frida](http://www.frida.re/). Specifically, it spawns the trainer and re-injects into its child processes until it intercepts file management calls to `*.CETRAINER` files. Then, if necessary, it will decrypt it to the plaintext (i.e. unprotected) XML version.

__WARNING__: Since this method actually executes the target trainer, for security reasons make sure everything is running in an isolated environment.

## 安装Frida
```
python pip install frida-tools
```

