# My Computer Setup:

## Applications To Install
* [Dropbox](https://www.dropbox.com)
* [Flux](https://justgetflux.com)
* [1Password](https://agilebits.com/downloads)
  * License is saved in the 1Password database. Double click it to apply.
* [BetterTouchTool](http://www.bettertouchtool.net)
  * Import Config from this repo.
* [MacID](http://macid.co)
* [Alfred](http://www.alfredapp.com)
* [Coconut Battery](http://www.coconut-flavour.com/coconutbattery/)
* [CoRD](http://cord.sourceforge.net)
* [Firefox](https://www.mozilla.org/en-US/firefox/)
* [Chrome](https://www.google.com/chrome/)
* Office
* [Paprika](http://paprikaapp.com)
  * Download from Mac App Store
* [RDM](https://dl.dropbox.com/u/87351306/RDM.tar.gz)
  * [Reddit Discussion](https://www.reddit.com/r/apple/comments/vi9yf/set_your_retina_macbook_pros_resolution_to)
  * See custom config in Config section, below.
* [Sublime Text](http://www.sublimetext.com)
  * See custom config in Config section, below.
* [Github](https://github.com)

## Configuration, Setup, and Customization:

### OS X Settings:

### Retina Display Configuration:
  * [Custom Resolutions with HiDPI](https://www.reddit.com/r/apple/comments/2ia242/enabling_1920_x_1200_hidpi_resolution_on_the_13/cl0c87l)
  	* Terminal> ioreg -lw0 | grep IODisplayPrefsKey 
  	* Look for: 
	"IODisplayPrefsKey" = "IOService:/AppleACPIPlatformExpert/PCI0@0/AppleACPIPCI/IGPU@2/AppleIntelFramebuffer@0/display0/AppleBacklightDisplay-610-a018"
    * The only thing we care about here is the 610 and the a018 though your numbers may be different.
    * We will want to navigate to /System/Library/Displays/Overrides/ in finder and choose the folder that corresponds with your first number, mine being 610. The folder I want is called DisplayVendorID-610.
    * Inside you want to find the corresponding files with your second number, mine being a018. The file I want is called DisplayProductID-a018.
    * To avoid dealing with getting rights to the file, we will just make a copy on the desktop and modify that. After that, open the copy you just made on the Desktop in TextEdit. Within the <array> portion you will want to make a new line and paste in <data>AAAPAAAACWAAAAAB</data>. This is the data for the 1920x1200 HiDPI resolution. Save this file.
    * Then you want to delete the original DisplayProductID-a018 (or whatever file yours is) and paste in yours from the desktop. Make sure the name matches exactly or it will not work.
    * Reboot your machine and switch the resolution in RDM when you boot up.

### Sublime Text Configuration:
  * [Add syntax Highlighting for Jade](http://stackoverflow.com/a/7693609)
```
  cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages
  git clone https://github.com/davidrios/jade-tmbundle Jade
```


