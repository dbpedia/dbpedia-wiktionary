dbpedia-wiktionary
==================

Precompiled executables, config files and working examples for http://dbpedia.org/Wiktionary

##Preamble
The jar file might be a bit outdated. The configs however are recent and up to date. They are included into the git repo here:
https://github.com/dbpedia/extraction-framework/tree/master/wiktionary
So please push ypur changes to here (Maybe we will refactor )

##Files & Folders
dbpedia-wiktionary.jar -> executable java file
config.properties.default -> default config file, please modify it to your needs
wiktionary-dump -> folder with input files, please download from http://dumps.wikimedia.org/backup-index.html
output -> folder for the created RDF files
config -> folder with config files, that configure how RDF triples are extracted

## Working example
After you checkout, you should be immeadiately able to run a working example:
<code>java -jar dbpedia-wiktionary-2013-03-27.jar config.properties.example example wiktionaryDump/house-example.xml.bz2 output/file.ttl</code>

Note: you can actually test and debug the xml by using just a single page via a special Wiktionary Export function. 
Just save this XML to the "wiktionaryDump" folder: http://en.wiktionary.org/wiki/Special:Export/house
<code>wget -O wiktionaryDump/house-example.xml http://en.wiktionary.org/wiki/Special:Export/house<code>
You can then test and extend it from there. Below are more detailed instructions


##Instructions
###Step 1: Download the Wiktionary XML dump
Go to the wikimedia dump archive at http://dumps.wikimedia.org/backup-index.html, search the latest version of the targeted language. 
Download the article dump file "[...]-pages-articles.xml" and put it into the “wiktionaryDump” folder.
Example with probably outdated dump:
<code>cd wiktionaryDump
wget http://dumps.wikimedia.org/dewiktionary/20130321/dewiktionary-20130321-pages-articles.xml.bz2
</code>
###Step 2: Main config
Copy the config.properties.default to config.properties and adjust it 
###Step 3: Check configuration in the folder "config"
* config.xml //general config for loglevel and language
* config-xx.xml // most action happens here, this is the language specific 
###Step 4: Run it
Usage: java -jar <xy.jar> <configfile> <language> <dumpFile> <outputFile>
Example:
<code>java -jar dbpedia-wiktionary-2013-03-27.jar config.properties de wiktionaryDump/dewiktionary-20130321-pages-articles.xml.bz2 output/file.ttl </code>


##Documentation
Everything else can be found here: http://dbpedia.org/Wiktionary
