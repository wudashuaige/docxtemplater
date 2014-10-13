# docxtemplater

[![Build Status](https://travis-ci.org/edi9999/docxtemplater.svg?branch=master)](https://travis-ci.org/edi9999/docxtemplater)
[![Download count](http://img.shields.io/npm/dm/docxtemplater.svg)](https://www.npmjs.org/package/docxtemplater)
[![Current tag](http://img.shields.io/npm/v/docxtemplater.svg)](https://www.npmjs.org/package/docxtemplater)

**docxtemplater** is a library to generate docx documents from a docx template. It can replace tags by their values and replace images with other images. It is very user oriented as users can without a lot of programming knowledge create their first template and automatically change variables in it.

## Documentation

The full documentation can be found on [read the docs](http://docxtemplater.readthedocs.org/en/latest/).

## Demo

[All demos can be found here](http://javascript-ninja.fr/docxgenjs/examples/demo.html)

Including:

- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#variables">Replace Variables</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#formating">Formating</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#parsing">Angular Parsing</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#loops">Loops</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#tables">Loops and tables</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#lists">Lists</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#images">Replacing images</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#naming">Naming the output</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#qrcode">Using QrCodes</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#qrcodeloop">Replacing many images with QrCode</a><br>
- <a href="http://javascript-ninja.fr/docxgenjs/examples/demo.html#rawxml">Raw Xml Insertion</a><br>


## Quickstart

Installation: `npm install docxtemplater`

    //Only for Node Usage
    DocxGen=require('docxtemplater'); 
    content=fs.readFileSync(__dirname+"/input.docx","binary")

    doc=new DocxGen(content);
    doc.setData({
        "first_name":"Hipp",
        "last_name":"Edgar",
        "phone":"0652455478",
        "description":"New Website"
    }) //set the templateVariables
    doc.render() //apply them (replace all occurences of {first_name} by Hipp, ...)
    zip=doc.getZip() //Get the zip representation of the docx

    //Only for Node Usage
    output=zip.generate({type:"base64"})
    fs.writeFileSync(__dirname+"/output.docx",output,"binary")

You can download [input.docx](https://github.com/edi9999/docxtemplater/raw/master/examples/tagExample.docx) and put it in the same folder than your script.

## Similar libraries

They are a few similar libraries that work with docx, here’s a list of those I know a bit about:

 * docx4j :JAVA, this is probably the biggest docx library out there. They is no built in templating engine, but you can generate your docx yourself programmatically 
 * docx.js: Javascript in the browser, you can create (not modify) your docx from scratch, but only do very simple things such as adding non formatted text

## Known issues

Todo:

 - [ ] Incompatibility with IE: Error : SCRIPT5022: End of stream reached (stream length = 14578, asked index = 18431). Corrupted zip ?
 - [ ] Use FileSaver API for output http://eligrey.com/blog/post/saving-generated-files-on-the-client-side
