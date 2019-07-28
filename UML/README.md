# Generating UML Diagrams

## Overview
This folder contains UML diagrams.
The diagrams are generated using plantuml and tplant
For an overview of how to create puml files manually see [here](http://plantuml.com/sitemap-language-specification)


## Pre requisites
Ensure plantuml and tplant are installed
```
brew install plantuml
npm install --global tplant
```


## Generate a diagram
This involves two steps
1. Generate the puml file based on the typescript file
2. Generate th png based on the puml file

```
cd /Users/jincubator/projects/cowri/gitbook/cowri-architecture/UML
tplant --input ../../../cowri-sdk/cowri-dapp-sdk/src/ShellManager.ts --output ShellManager.puml
plantuml ShellManager.puml 
```