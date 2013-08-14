dbpedia-wiktionary
==================

Precompiled executables, config files and working examples for http://dbpedia.org/Wiktionary

##Preamble
The jar file might be a bit outdated but we will periodically update it. 
The configurations are kept in a [separate repository](https://github.com/dbpedia/dbpedia-wiktionary-configuration) 
to ease contributions and are linked both from this repo, as well as the [DBpedia extraction framework](https://github.com/dbpedia/extraction-framework/).
So please push your changes [there](https://github.com/dbpedia/dbpedia-wiktionary-configuration) .

##Files & Folders
* dbpedia-wiktionary.jar -> executable java file
* config.properties.default -> default config file, please modify it to your needs
* sample-xml-dumps -> folder with example input files
* config -> folder with config files, that configure how RDF triples are extracted

The DBpedia framework has an automated download mechanism to download dumps from: http://dumps.wikimedia.org/backup-index.html
Documentation is being moved to the main Githib Wiki: https://github.com/dbpedia/extraction-framework/wiki

## Working example
After you checkout run the following Git commands to fetch the latest configuration:
<code>git submodule update --init --recursive</code><br/>
<code>git submodule foreach git pull #This can be run periodically to fetch possible configuration updates</code>

Then you should be immeadiately able to run a working example:
<code>java -jar dbpedia-wiktionary-2013-04-04.jar config.properties.default</code>

This should create output files in the respective folder, e.g. sample-xml-dumps/dewiktionary/20130321/
So in the config.properties.default "de" is enabled by "languages=en,de,el,fr", which means you can find the output file here:
sample-xml-dumps/dewiktionary/20130321/dewiktionary-20130321-wiktionary.dbpedia.org.ttl

Note: you can actually test and debug the xml by using just a single page via a special Wiktionary Export function. 
Just save this XML to the "wiktionaryDump" folder: http://en.wiktionary.org/wiki/Special:Export/house
<code>wget -O wiktionaryDump/house-example.xml http://en.wiktionary.org/wiki/Special:Export/house<code>
You can then test and extend it from there. Below are more detailed instructions


##Instructions (outdated!)
**Note these instructions are more guidelines, we will push documentation here, as soon as we are finished with the main framework**
###Step 1: Download the Wiktionary XML dump
Go to the wikimedia dump archive at http://dumps.wikimedia.org/backup-index.html, search the latest version of the targeted language. 
Download the article dump file "[...]-pages-articles.xml" and put it into  “wiktionaryDump” folder.
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
Usage: java -jar <xy.jar> <configfile> 
Example:
<code>java -jar dbpedia-wiktionary-2013-03-27.jar config.properties </code>


##Documentation
Everything else can be found here: http://dbpedia.org/Wiktionary
