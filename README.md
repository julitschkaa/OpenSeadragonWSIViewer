# OpenSeadragonWSIViewer
Simple setup for a browserbased WSI Viewer

1. Download CMU-1.tiff from http://openslide.cs.cmu.edu/download/openslide-testdata/Generic-TIFF/CMU-1.tiff
2. Download Cantaloupe image server from https://cantaloupe-project.github.io/

   1. extract zip-file and open a file called cantaloupe.properties.sample in any text-editor.
   2. in this file set FilesystemSource.BasicLookupStrategy.path_prefix to a folder path containing your CMU-1.tiff from Step 1.
   3. save file as cantaloupe.properties
  
3. Open a terminal in your cantaloupe-directory and run
    `java -Dcantaloupe.config=cantaloupe.properties -Xmx2g -jar cantaloupe-4.1.7.war`
4. Open http://localhost:8182/iiif/2/CMU-1.tiff/info.json in your preferred browser
   1. this is where you get your width and height of your image and also, the size of your tiles as well as scalefactors.
5. Insert your aforementioned numbers into your html file, specifically into your OpenSeadragonViewer instance.
6. For the tileSources: set "@context": "http://iiif.io/api/image/2/context.json",and "@id": "http://localhost:8182/iiif/2/CMU-1.tiff".
7. In order to show the Navigator in your viewer, set:
         'showNavigator:  true,
          navigatorPosition: 'BOTTOM_RIGHT',
          navigatorAutoFade:  false,'
