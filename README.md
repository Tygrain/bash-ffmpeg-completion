# bash-ffmpeg-completion

Bash completion support and custom macro substitution for ffmpeg options.

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
![list ffmpeg's options](https://tygrain.github.io/master/images/ffmpeg-options-min.gif)
To complete option:
```sh
$ ffmpeg -i in.mp4 -cod[TAB]
-codec   -codecs  -colors
```
To list ffmpeg's options:
```sh
$ ffmpeg -[TAB][TAB]
```
![to complete video or audio codec](https://tygrain.github.io/master/images/ffmpeg-codecs-min.gif)
To complete video or audio codec:
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
![parameter substitution](https://tygrain.github.io/master/images/ffmpeg-macros-min.gif)
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
