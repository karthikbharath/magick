# magick

##### *Advanced Image-Processing in R*

[![Build Status](https://travis-ci.org/jeroenooms/magick.svg?branch=master)](https://travis-ci.org/jeroenooms/magick)
[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/jeroenooms/magick?branch=master&svg=true)](https://ci.appveyor.com/project/jeroenooms/magick)
[![Coverage Status](https://codecov.io/github/jeroenooms/magick/coverage.svg?branch=master)](https://codecov.io/github/jeroenooms/magick?branch=master)
[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/magick)](http://cran.r-project.org/package=magick)
[![CRAN RStudio mirror downloads](http://cranlogs.r-pkg.org/badges/magick)](http://cran.r-project.org/web/packages/magick/index.html)
[![Github Stars](https://img.shields.io/github/stars/jeroenooms/magick.svg?style=social&label=Github)](https://github.com/jeroenooms/magick)

> Bindings to ImageMagick: the most comprehensive open-source image
  processing library available. Supports many common formats (png, jpeg, tiff,
  pdf, etc) and manipulations (rotate, scale, crop, trim, flip, blur, etc).
  All operations are vectorized via the Magick++ STL meaning they operate either
  on a single frame or a series of frames for working with layers, collages,
  video, or animation. Images are automatically previewed when printed to the
  console in RStudio or an X11 GUI, creating a fully interactive environment

## Documentation

About the underlying library:

 - [Magick++ STL Documentation](https://www.imagemagick.org/Magick++/STL.html)

## Hello World

Run the examples in RStudio to see a live previews of the images!

```r
# Download image from the web
frink <- image_read("https://jeroenooms.github.io/images/frink.png")
print(frink)

frink2 <- image_trim(frink)
image_write(frink2, "output.png")



# Convert to formats
image <- magick::image_read(png_file)
magick::image_write(image, "output.jpg", format = "jpg")
magick::image_write(image, "output.gif", format = "gif")
magick::image_write(image, "output.pdf", format = "pdf")

```

## Installation

Binary packages for __OS-X__ or __Windows__ can be installed directly from CRAN:

```r
install.packages("magick")
```

Installation from source on Linux or OSX requires the imagemagick [`Magick++`](https://www.imagemagick.org/Magick++/Documentation.html) library. On __Debian or Ubuntu__ install [libmagick++-dev](https://packages.debian.org/testing/libmagick++-dev):

```
sudo apt-get install -y libmagick++-dev
```

On __Fedora__,  __CentOS or RHEL__ we need [ImageMagick-c++-devel](https://apps.fedoraproject.org/packages/ImageMagick-c++-devel):

```
sudo yum install ImageMagick-c++-devel
````

On __OS-X__ use [imagemagick](https://github.com/Homebrew/homebrew-core/blob/master/Formula/imagemagick.rb) from Homebrew:

```
brew install imagemagick
```

There is also a fork of imagemagick called graphicsmagick, but it doesn't work as well. I highly recommend you build with imagemagick.

[![](http://ropensci.org/public_images/github_footer.png)](http://ropensci.org)
