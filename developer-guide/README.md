
shell-manager
=============

Shell Manager

Developer setup
---------------

```
git clone https://github.com/cowri/shell-manager.git
npm install
npm run clean
npm run build
npm run test
```

Testing
-------

Testing of the shell-manager is separated into two categories: unit and integration. The unit tests do not have any external dependencies while the integration tests require that a local instance of Ganache-cli is running as the Denise user. Installation instructions for Ganache-cli can be found in [Installation.MD](https://github.com/cowri/shell-manager/blob/master/Installation.MD).

*   Run unit tests with `npm run test:watch`
*   To run integration tests, start up the local instance of Ganache-cli with `ganache-cli --networkId 50 -p 8545 --db ./Cowri_0x_ganache_snapshot -m "concert load couple harbor equip island argue ramp clarify fence smart topic" --account="0xC31301245F18B4649ED80349C237B32FF76DCB8A727DBF6A271DE5B97515000E,100000000000000000000"` and then run the tests with `npm run test:integration`
    
    ### Mocks
    
    Mocks are used as a replacement for external dependencies when running unit tests as apposed to using the dependencies for integration tests. For example, rather than the unit tests depending on a local instance of Ganache-cli running, the unit tests use mocks.
    

Pushing to NPM
--------------

```
npm publish

For the time being these two following commands are removed.
When the tests are completing healthily, they will be put back
in to the scripts portion of package.json, which will test 
the repository before publication of new versions.

  "prepare": "npm run build",
  "prepublishOnly": "npm run test && npm run lint",

```

Generating Documentation
------------------------

Currently documentation generation is set up to go the [gitbook repsoitory](https://github.com/cowri) Publishing process

1.  Clone [gitbook repsoitory](https://github.com/cowri) into the same parent directory as shell-manager
2.  generate the documentation e.g. `npm run docs ./src/provider/CowriWeb3Provider.ts`
3.  **Note**
    *   when using `npm run docs` you must specify the directory of file you want to create documentation for (as above)
    *   If you would like to use a different destination directory for documentation you can use the following command `.node_modules/.bin/typedoc --theme markdown --mdEngine gitbook --out ../gitbook/typedoc/ ./src/provider/CowriWeb3Provider.ts`

