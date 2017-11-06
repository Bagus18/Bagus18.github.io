---
layout: post
title:  "Automatic Image Loader"
date:   2015-01-15 11:18:29 +7
categories: code php
tags : images
---

<h2>ABOUT</h2>
   <p> This PHP script will randomly select an image file from a
    folder of images on your webserver.  You can then link to it
    as you would any standard image file and you'll see a random
    image each time you reload. When you want to add or remove images from the rotation-pool,
    just add or remove them from the image rotation folder.</p>

<h2>INSTRUCTIONS</h2>
<p> 1. Modify the $folder setting in the configuration section below.<br />2. Add image types if needed (most users can ignore that part).<br />3. Upload this file (rotate.php) to your webserver.  I recommend uploading it to the same folder as your images.<br />4. Link to the file as you would any normal image file, like this:
{% highlight html %}
            <img src="http://example.com/images/logo/logo.php">{% endhighlight %}

<p>5. You can also specify the image to display like this:</p>
{% highlight html %} <img src="http://example.com/images/logo/rotate.php?img=big.png">{% endhighlight %}
<p>This would specify that an image named "big.png" located in the images-rotation folder should be displayed.</p>
<p>That's it, you're done.</p>
{% highlight php %}
/* ------------------------- CONFIGURATION -----------------------


    Set $folder to the full path to the location of your images.
    For example: $folder = '/user/me/example.com/images/';
    If the rotate.php file will be in the same folder as your
    images then you should leave it set to $folder = '.';

*/


    $folder = '.';


/*  

    Most users can safely ignore this part.  If you're a programmer,
    keep reading, if not, you're done.  Go get some coffee.

    If you'd like to enable additional image types other than
    gif, jpg, and png, add a duplicate line to the section below
    for the new image type.
    
    Add the new file-type, single-quoted, inside brackets.
    
    Add the mime-type to be sent to the browser, also single-quoted,
    after the equal sign.
    
    For example:
    
    PDF Files:

        $extList['pdf'] = 'application/pdf';
    
    CSS Files:

        $extList['css'] = 'text/css';

    You can even serve up random HTML files:

        $extList['html'] = 'text/html';
        $extList['htm'] = 'text/html';

    Just be sure your mime-type definition is correct!

*/

    $extList = array();
    $extList['gif'] = 'image/gif';
    $extList['jpg'] = 'image/jpeg';
    $extList['jpeg'] = 'image/jpeg';
    $extList['png'] = 'image/png';
    

// You don't need to edit anything after this point.


// --------------------- END CONFIGURATION -----------------------

$img = null;

if (substr($folder,-1) != '/') {
    $folder = $folder.'/';
}

if (isset($_GET['img'])) {
    $imageInfo = pathinfo($_GET['img']);
    if (
        isset( $extList[ strtolower( $imageInfo['extension'] ) ] ) &&
        file_exists( $folder.$imageInfo['basename'] )
    ) {
        $img = $folder.$imageInfo['basename'];
    }
} else {
    $fileList = array();
    $handle = opendir($folder);
    while ( false !== ( $file = readdir($handle) ) ) {
        $file_info = pathinfo($file);
        if (
            isset( $extList[ strtolower( $file_info['extension'] ) ] )
        ) {
            $fileList[] = $file;
        }
    }
    closedir($handle);

    if (count($fileList) > 0) {
        $imageNumber = time() % count($fileList);
        $img = $folder.$fileList[$imageNumber];
    }
}

if ($img!=null) {
    $imageInfo = pathinfo($img);
    $contentType = 'Content-type: '.$extList[ $imageInfo['extension'] ];
    header ($contentType);
    readfile($img);
} else {
    if ( function_exists('imagecreate') ) {
        header ("Content-type: image/png");
        $im = @imagecreate (100, 100)
            or die ("Cannot initialize new GD image stream");
        $background_color = imagecolorallocate ($im, 255, 255, 255);
        $text_color = imagecolorallocate ($im, 0,0,0);
        imagestring ($im, 2, 5, 5,  "IMAGE ERROR", $text_color);
        imagepng ($im);
        imagedestroy($im);
    }
}

?>
{% endhighlight %}