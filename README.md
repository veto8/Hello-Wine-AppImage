# hello_wine_imageapp
Example of running a Windows EXE program from a Linux app image

## Build it
```
git clone https://github.com/myridia/Hello-Wine-AppImage.git
cd Hello-Wine-AppImage 
sudo chmod +x appimagetool-x86_64.AppImage 
ARCH=x86_64 ./appimagetool-x86_64.AppImage  hello.AppDir/ 
```

## Run it
```
sudo chmod +x Hello-x86_64.AppImage 
./Hello-x86_64.AppImage 
```

## Example as Release
The Release https://github.com/myridia/Hello-Wine-AppImage/releases is build by the action https://github.com/myridia/Hello-Wine-AppImage/blob/main/.github/workflows/linux.yml


## Background
* To make it work, we need a portable wine and you can find it wine-stable_11.0-x86_64.AppImage, the maintainer is https://github.com/mmtrt/WINE_AppImage 
* We use a pre-build prefix  https://github.com/myridia/Hello-Wine-AppImage/tree/main/hello.AppDir/prefix.
* Because AppImage use a  readonly filesystem we need to export this prefix to the the home directory of the use when the user starts the AppImage the first time 



## Extras 
### Test action 
cd .github/workflow/
act -W linux.yml --verbose -P docker3=myridia/runner --pull=false
