[![Latest Stable Version](https://poser.pugx.org/dinesh/barcode/v/stable.png)](https://packagist.org/packages/dinesh/barcode)
[![Total Downloads](https://poser.pugx.org/dinesh/barcode/downloads.png)](https://packagist.org/packages/dinesh/barcode)
[![Build Status](https://travis-ci.org/dineshrabara/barcode.png?branch=master)](https://travis-ci.org/dineshrabara/barcode)

[Read More Wiki](https://github.com/dineshrabara/barcode/wiki)

## Installation

Begin by installing this package through Composer. Edit your project's `composer.json` file to require `dinesh/barcode`.

    "require": {
		"laravel/framework": "4.0.*",
		"dinesh/barcode": "dev-master"
	}

Next, update Composer from the Terminal:

    composer update

Once this operation completes, the final step is to add the service provider. Open `app/config/app.php`, and add a new item to the providers array.

    'Dinesh\Barcode\BarcodeServiceProvider'

If you want to change Bar-code's settings (Store Path etc.), you need to publish its config file(s).

    Run php artisan config:publish dinesh/barcode 

Now add the alias.
```php
'aliases' => array(
	'DNS1D' => 'Dinesh\Barcode\Facades\DNS1DFacade',
        'DNS2D' => 'Dinesh\Barcode\Facades\DNS2DFacade',
)
```

from the command line and you should find the files in app/config/packages/dinesh/barcode.


Bar-code generator like 
Qr Code,
PDF417,
C39,C39+,
C39E,C39E+,
C93,
S25,S25+,
I25,I25+,
C128,C128A,C128B,C128C,
2-Digits UPC-Based Extention,
5-Digits UPC-Based Extention,
EAN 8,EAN 13,
UPC-A,UPC-E,
MSI (Variation of Plessey code)

generator in html, png embedded base64 code and SVG canvas 


    echo DNS1D::getBarcodeSVG("4445645656", "PHARMA2T");
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T");
    echo '<img src="data:image/png,' . DNS1D::getBarcodePNG("4", "C39+") . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T");
    echo '<img src="data:image/png,' . DNS1D::getBarcodePNG("4", "C39+") . '" alt="barcode"   />';



    echo DNS1D::getBarcodeSVG("4445645656", "C39");
    echo DNS2D::getBarcodeHTML("4445645656", "QRCODE");
    echo DNS2D::getBarcodePNGPath("4445645656", "PDF417");
    echo DNS2D::getBarcodeSVG("4445645656", "DATAMATRIX");
    echo '<img src="data:image/png,' . DNS2D::getBarcodePNG("4", "PDF417") . '" alt="barcode"   />';


## Width and Height example

    echo DNS1D::getBarcodeSVG("4445645656", "PHARMA2T",3,33);
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T",3,33);
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33) . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T",3,33);
    echo '<img src="data:image/png,' . DNS1D::getBarcodePNG("4", "C39+",3,33) . '" alt="barcode"   />';
    
    
## Color


    echo DNS1D::getBarcodeSVG("4445645656", "PHARMA2T",3,33,"green");
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T",3,33,"green");
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33,array(1,1,1)) . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T",3,33,array(255,255,0));
    echo '<img src="data:image/png,' . DNS1D::getBarcodePNG("4", "C39+",3,33,array(1,1,1)) . '" alt="barcode"   />';


## 2D Barcodes

    echo DNS2D::getBarcodeHTML("4445645656", "QRCODE");
    echo DNS2D::getBarcodePNGPath("4445645656", "PDF417");
    echo DNS2D::getBarcodeSVG("4445645656", "DATAMATRIX");     

## 1D Barcodes

    echo DNS1D::getBarcodeHTML("4445645656", "C39");
    echo DNS1D::getBarcodeHTML("4445645656", "C39+");
    echo DNS1D::getBarcodeHTML("4445645656", "C39E");
    echo DNS1D::getBarcodeHTML("4445645656", "C39E+");
    echo DNS1D::getBarcodeHTML("4445645656", "C93");
    echo DNS1D::getBarcodeHTML("4445645656", "S25");
    echo DNS1D::getBarcodeHTML("4445645656", "S25+");
    echo DNS1D::getBarcodeHTML("4445645656", "I25");
    echo DNS1D::getBarcodeHTML("4445645656", "I25+");
    echo DNS1D::getBarcodeHTML("4445645656", "C128");
    echo DNS1D::getBarcodeHTML("4445645656", "C128A");
    echo DNS1D::getBarcodeHTML("4445645656", "C128B");
    echo DNS1D::getBarcodeHTML("4445645656", "C128C");
    echo DNS1D::getBarcodeHTML("44455656", "EAN2");
    echo DNS1D::getBarcodeHTML("4445656", "EAN5");
    echo DNS1D::getBarcodeHTML("4445", "EAN8");
    echo DNS1D::getBarcodeHTML("4445", "EAN13");
    echo DNS1D::getBarcodeHTML("4445645656", "UPCA");
    echo DNS1D::getBarcodeHTML("4445645656", "UPCE");
    echo DNS1D::getBarcodeHTML("4445645656", "MSI");
    echo DNS1D::getBarcodeHTML("4445645656", "MSI+");
    echo DNS1D::getBarcodeHTML("4445645656", "POSTNET");
    echo DNS1D::getBarcodeHTML("4445645656", "PLANET");
    echo DNS1D::getBarcodeHTML("4445645656", "RMS4CC");
    echo DNS1D::getBarcodeHTML("4445645656", "KIX");
    echo DNS1D::getBarcodeHTML("4445645656", "IMB");
    echo DNS1D::getBarcodeHTML("4445645656", "CODABAR");
    echo DNS1D::getBarcodeHTML("4445645656", "CODE11");
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA");
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T");
