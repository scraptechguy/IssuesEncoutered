# Welcome in Windows HOWTO! 

Before anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks! 

## Kivy

+ Never name python (or any) file the same as a library you are using. Python prioritises python file over library with the same name.


## PyAudio installation 

### Instalation (Windows 10): 

+ Required libraries: pip

+ Install PyAudio package from website below. Choose based on python version (cp39 -> python 3.9).

      https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio

For me it's: PyAudio‑0.2.11‑cp39‑cp39‑win_amd64.whl

+ Locate the file and access the folder with PyAudio using terminal. 

      cd /c/Users/rosti/Downloads
  
+ And run command...
 
       pip install PyAudio‑0.2.11‑cp39‑cp39‑win_amd64.whl
