# Kolourmeans
An application that turns locations selected on a satellite map into colour palettes.
# How it works!
- The interactive map uses the javascript library [Leaflet](https://leafletjs.com/).
- [Axios](https://www.npmjs.com/package/axios) is used to turn the url of the image to a UInt8Array, then to an Electron nativeImage to turn into a bitmap of pixel data.
- 5 random colours in the image are selected as centeroids.
- Euclidean distance is used to calculate the distance between each rgb colour and each centeroid, then grouped together with the closest one to form clusters.
- The centeroid is recalculated by averaging the points in the cluster, then the colours are reassigned to the closest centeroid & repeat process ~5 times (in a better k means algorithm, it would repeat until the colours stop changing, however i find just re-assigning them a few times works well too.)
- the centeroids are sorted by light to dark through turning them to cieLab colours and sorting by the L(ight) value, alternatively, the eucalidean distance algorithm could also be used here to sort by overall distance between each colour in a 3D space.
# Download 
1. Dowload the latest release.
2. Extract files from zip.
3. Run the application file.
# Development
1. Clone the repository
```
git clone https://github.com/variidian/kolourmeans
```
2. Navigate to project & install dependencies
```
cd (project location)
npm install
```
3. Run
```
npm run start
```
# Notes
- The naming of this project comes from the words 'colour' as in 'colour palettes' and 'k-means clustering', the algorithm used to turn the colours in the image into a nice-looking palette.
- Smol bit inspired by [@phthallo's pyflagoras project](https://github.com/phthallo/pyflagoras) 
