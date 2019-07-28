* Generate Code Documentation
```
cdc
cd cowri-sdk/cowri-dapp-sdk
./node_modules/.bin/typedoc --theme markdown --mdEngine gitbook --mode modules  --disableOutputCheck --readme none --excludePrivate  --hideGenerator --excludeExternals --out ../../gitbook/cowri-reference/  ./src/ShellManager.ts

# gitbook serve --port 4001 --no-live
# Modify Developer reference section if needed
```

* Generate UML
```
cd /Users/jincubator/projects/cowri/gitbook/UML
plantuml Overview.puml
mv Overview.png ../img/
```

* Test gitbook
```

cd /Users/jincubator/projects/cowri/gitbook/cowri-reference
python -m SimpleHTTPServer 8000

cd /Users/jincubator/projects/cowri/gitbook/cowri-reference
gitbook serve --port 4001 --no-live

cd /Users/jincubator/projects/cowri/gitbook
gitbook serve
```

* Publish gitbook - commit
