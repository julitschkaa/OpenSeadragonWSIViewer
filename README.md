# OpenSeadragonWSIViewer
Simple setup for a browserbased WSI Viewer

1. Download CMU-1.tiff from http://openslide.cs.cmu.edu/download/openslide-testdata/Generic-TIFF/CMU-1.tiff
2. Download Cantaloupe image server from https://cantaloupe-project.github.io/

   1. extract zip-file and open a file called cantaloupe.properties.sample in any text-editor.
   2. in this file set FilesystemSource.BasicLookupStrategy.path_prefix to a folder path containing your CMU-1.tiff from Step 1.
   3. save file as cantaloupe.properties
  
3. Open a terminal in your cantaloupe-directory and type 
    `java -Dcantaloupe.config=/path/to/cantaloupe.properties -Xmx2g -jar cantaloupe-x.x.x.war`
