dbpedia-wiktionary
==================

Precompiled executables, config files and working examples for http://dbpedia.org/Wiktionary


##Files & Folders

dbpedia-wiktionary.jar -> executable java file
config.properties.default -> default config file, please modify it to your needs
wiktionary-dump -> folder with input files, please download from http://dumps.wikimedia.org/backup-index.html
output -> folder for the created RDF files
config -> folder with config files, that configure how RDF triples are extracted

##Instructions
1. copy config.properties.default to config.properties
2. modify config.properties and adjust it to your needs
3. modify the correct config xml file in the config folder
4. run "java -jar dbpedia-wiktionary.jar ......"


##Documentation
Everything else can be found here: http://dbpedia.org/Wiktionary
