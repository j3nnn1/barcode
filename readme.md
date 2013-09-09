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

from the command line and you should find the files in app/config/packages/dinesh/barcode.


Bar-code generator like 
Qr Code,
PDF147,
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
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+") . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T");
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+") . '" alt="barcode"   />';



    echo DNS1D::getBarcodeSVG("4445645656", "C39");
    echo DNS2D::getBarcodeHTML("4445645656", "QRCODE");
    echo DNS2D::getBarcodePNGPath("4445645656", "PDF417");
    echo DNS2D::getBarcodeSVG("4445645656", "DATAMATRIX");
    echo '<img src="' . DNS2D::getBarcodePNG("4", "PDF417") . '" alt="barcode"   />';


## Width and Height example

    echo DNS1D::getBarcodeSVG("4445645656", "PHARMA2T",3,33);
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T",3,33);
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33) . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T",3,33);
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33) . '" alt="barcode"   />';
    
    
## Color


    echo DNS1D::getBarcodeSVG("4445645656", "PHARMA2T",3,33,"green");
    echo DNS1D::getBarcodeHTML("4445645656", "PHARMA2T",3,33,"green");
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33,array(1,1,1)) . '" alt="barcode"   />';
    echo DNS1D::getBarcodePNGPath("4445645656", "PHARMA2T",3,33,array(255,255,0));
    echo '<img src="' . DNS1D::getBarcodePNG("4", "C39+",3,33,array(1,1,1)) . '" alt="barcode"   />';

