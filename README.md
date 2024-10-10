# MacOS AMD Adobe Fix
Hi! There is a really working macos amd fix for adobe products: photoshop / premier and etc (hackintosh). Tested on my Ryzentosh. 

Before any manipulations install amdfriend from this repo: https://github.com/NyaomiDEV/AMDFriend. It's archived, so you can just download from releases section and add it to your path

## AMD fix for Adobe Photoshop 2024
1) put the command:
```
sudo amdfriend --dry-run --directories /Applications/Adobe\ Premiere\ Pro\ 2024/Adobe\ Premiere\ Pro\ 2024.app/Contents/Frameworks | grep "Routines found"
```
2) it will show all the paths with *.dylib files that are need to be patched. 
3) patch with --in-place --sign flags
4) should be similar to this:
```
sudo amdfriend --dry-run --directories /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks | grep "Routines found"  
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libippik0.dylib  
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_avx2.2.dylib  
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_mc3.2.dylib  
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_avx512.2.dylib  
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_core.2.dylib
```

##  AMD fix to Adobe Premier 2024
1) put the command:
```
sudo amdfriend --dry-run --directories /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks | grep "Routines found"
```
2) it will show all the paths with *.dylib files that are need to be patched
3) patch with --in-place --sign flags
4) should be similar to this:
```
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libippik0.dylib
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_avx2.2.dylib
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_mc3.2.dylib
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_avx512.2.dylib
sudo amdfriend --in-place --sign /Applications/Adobe\ Photoshop\ 2024/Adobe\ Photoshop\ 2024.app/Contents/Frameworks/libmkl_core.2.dylib
```

## Other
Try to use the same method to fix other adobe products if there are any errors. 

## Thanks to:
- https://macos86.it/topic/5603-discussion-amdfriend-for-almost-all-of-your-library-patching-needs
