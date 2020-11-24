# bash-ffmpeg-completion

Bash completion support and custom macro substitution for ffmpeg options.

Check that **bash-сompletion** is connected to your shell before installing
```sh
$ complete -p
complete -F _longopt mv
complete -F _root_command gksudo
complete -F _command nice
complete -F _longopt tr
complete -F _longopt head
complete -F _longopt sha256sum
...
```
if you encounter any errors, then use the installation instructions **bash-сompletion** for your system and only then proceed with the installation.
### Installation
Global:
```sh
git clone https://github.com/Tygrain/bash-ffmpeg-completion.git
sudo cp ./bash-ffmpeg-completion/ffmpeg-completion /etc/bash_completion.d/ffmpeg-completion
```
Local:
```sh
git clone https://github.com/Tygrain/bash-ffmpeg-completion.git
[ -d "$HOME/bash_completion.d" ] || mkdir ~/bash_completion.d
cp ./bash-ffmpeg-completion/ffmpeg-completion ~/bash_completion.d/ffmpeg-completion
echo "" >> ~/.bashrc
echo 'if [ -f "$HOME/bash_completion.d/ffmpeg-completion" ] ; then' >> ~/.bashrc
echo '    source $HOME/bash_completion.d/ffmpeg-completion' >> ~/.bashrc
echo "fi" >> ~/.bashrc
```
### Usage
To complete option:

![list ffmpeg's options](https://tygrain.github.io/images/ffmpeg-options-min.gif)

```sh
$ ffmpeg -i in.mp4 -cod[TAB]
-codec   -codecs  -colors
```
To list ffmpeg's options:
```sh
$ ffmpeg -[TAB][TAB]
```
To complete video or audio codec:

![to complete video or audio codec](https://tygrain.github.io/images/ffmpeg-codecs-min.gif)

```sh
$ ffmpeg -i in.mp4 -c:v libx[TAB]
libx264     libx264rgb  libx265     libxvid
```
To list ffmpeg's video or audio codecs:
```sh
$ ffmpeg -i in.mp4 -c:v [TAB][TAB]
a64multi         flv              libwebp          pam              targa
a64multi5        gif              libwebp_anim     pbm              tiff
...
```
#### Custom parameter substitutions

![parameter substitution](https://tygrain.github.io/images/ffmpeg-macros-min.gif)

Create new substitution:
```sh
ffmpeg-macros-ci add macroname
```
Use substitution in ffmpeg parameter string:
```sh
ffmpeg -i in.mp4 @macroname[TAB]
```
Remove macro:
```sh
ffmpeg-macros-ci remove macroname
```

Thanks to [ANNiMON](https://github.com/aNNiMON/) for the idea of custom macros in the parameter line :)
