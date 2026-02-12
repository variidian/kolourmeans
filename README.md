# kolourmeans
An application that turns locations selected on a satellite map into colour palettes.
# how it works!
- The interactive map uses the javascript library [Leaflet] (https://leafletjs.com/)
- The zoom and the equivalent tileX and tileY is calculated from the latitude and longitude of the location the user clicks in order to get the equivalent image url
- [Axios] (https://www.npmjs.com/package/axios) is used to turn the url of the image to a UInt8Array, then to an Electron nativeImage to turn into a bitmap of pixel data 
- The rgba codes are added to an array with a for loop
- further explanation here! k means clustering algorithm.
# notes
- The naming of this project comes from the words 'colour' as in 'colour palettes' and 'k-means clustering', the algorithm used to turn the colours in the image into a nice-looking palette.
- Smol bit inspired by [@phthallo's pyflagoras project] (https://github.com/phthallo/pyflagoras) 
