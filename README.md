FCAM script (Fix Common Arabic Mistakes).
=========================================

Open/LibreOffice macros (Basic and Python) use Regex to fix common Arabic mistakes. For now both of Basic and Python versions do the same thing, but I will go with Python from now on.

What's it doing?
-------------------
- Removes any empty lines.
- Removes Arabic Kashida (Tatweel "ـ").
- Removes whitespaces after single WAW letter (و).
- Removes whitespaces before Arabic punctuation (؛،.؟:!).
- Removes any sequence of question and exclamation marks and replace them with one only (e.g. "!!!" and "??").
- Removes whitespaces in inside brackets "()" and "[]".
- Removes any sequence of whitespaces and whitespaces at end of lines.
- Replaces Latin comma (decimal separator) "," after Arabic words to Arabic comma "،".
- Replaces Latin semicolon ";" after Arabic words to Arabic semicolon "؛".

Basic version.
-------------------
Just copy the code into built-in macros editor.


Python version.
-------------------
By default Open/LibreOffice supports Basic natively, and if you want to use python macros, you have to install an extra package.

For Ubuntu:
```
sudo apt-get install libreoffice-script-provider-python
```

### Install
Copy the macro to scripts path.

Global path to make it available for all users:
```
/usr/lib/libreoffice/share/Scripts/python/
```

**OR** under your home:
```
~/.config/libreoffice/4/user/Scripts/python/
```

### Run
From the menu:
```
Tools ▸ Macros ▸ Run Macro ▸ LibreOffice Macros ▸ FixCommonArabicMistakes-Python
```

<p align="center">
<img src="http://3.bp.blogspot.com/-onSnFwBXg8o/Vk9WbSOLhKI/AAAAAAAACJc/4aEiIB2Pop4/run_python_libreoffice_macros.png" width="320">
</p>

Standalone version.
-------------------
I made a Standalone version of script too, it useful with bulk files or so, it maybe not that cool, but maybe help someone :-)

This script not works as a macro but will start Opne/LibreOffice on a specific local port and connect to it, then open the file passed to it, and fix common mistakes. It will not save the file automatically, but it will wait you to do save as a final action.

### Run:
```
./FixCommonArabicMistakes-Standalone.py file_name.odt
```
