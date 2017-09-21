---
layout: post
title:  "Google page speed checks"
date:   2017-09-21 09:00:00 +1000
categories: digitalmarketing
url: google-page-speed-checks
---

> The purpose of this documentation is to identify the main offenders in reference to a page speed report. A series of tests will be carried out on fixing these problems. Notes on which improve the score the most will be recommended.

[Google PageSpeed Insights]

## Optimizing

Optimizing and image refers to the ability to make the file a smaller file size. A technique for reducing the file size is compression or delivering scaled image assets. "We are definitely not in a position to invent new compression techniques, but it's important to understand the shape of the problem: RGBA pixels, bit-depth, and various optimization techniques." [Image Optimization] Optimizing an image is directly referenced to the data stored in individual pixels. Reading the [Image Optimization] page from Google helps understand how to optimize raster images effectively.  

### Compression

'Image compression is a type of data compression applied to digital images, to reduce their cost for storage or transmission.' [Image compression]

#### Lossless vs lossy image compression

Reading the heading [Lossless vs lossy image compression] from Google will give a more detailed reading of the key points below. The different types of compression are instigated by the file format you use. They use different algorithms to encode the data stored in a file.

Lossy compression: or irreversible compression is the class of data encoding methods that uses inexact approximations and partial data discarding to represent the content. These techniques are used to reduce data size for storage, handling, and transmitting content.

Lossless compression: is a class of data compression algorithms that allows the original data to be perfectly reconstructed from the compressed data.

By contrast, lossy compression permits reconstruction only of an approximation of the original data, though this usually improves compression rates (and therefore reduces file sizes).

A typical image optimization pipeline consists of two high level steps:

1. Image is processed with a "[lossy]" filter that eliminates some pixel data
2. Image is processed with a "[lossless]" filter that compresses the pixel data

"So, what is the "optimal" configuration of lossy and lossless optimization? The answer depends on the image contents and your own criteria such as the tradeoff between filesize and artifacts introduced by lossy compression: in some cases you may want to skip lossy optimization to communicate intricate detail in its full fidelity, and in others you may be able to apply aggressive lossy optimization to reduce the filesize of the image asset. This is where your own judgment and context need to come into play - there is no one universal setting.

As a hands-on example, when using a lossy format such as JPEG, the compressor will typically expose a customisable "quality" setting (for example, the quality slider provided by the "Save for Web" functionality in Adobe Photoshop), which is typically a number between 1 and 100 that controls the inner workings of the specific collection of lossy and lossless algorithms. For best results, experiment with various quality settings for your images, and don't be afraid to dial down the quality - the visual results are often very good and the filesize savings can be quite large."

#### What file type should I be using (PNG or JPEG)

Do you need to preserve fine detail with highest resolution? Use PNG.

- PNG does not apply any lossy compression algorithms beyond the choice of the size of the color palette. As a result, it will produce the highest quality image, but at a cost of significantly higher filesize than other formats. Use judiciously.

- If the image asset contains imagery composed of geometric shapes, consider converting it to a vector (SVG) format!

- If the image asset contains text, stop and reconsider. Text in images is not selectable, searchable, or "zoomable". If you need to convey a custom look (for branding or other reasons), use a web font instead.

Are you optimizing a photo, screenshot, or a similar image asset? Use JPEG.

- JPEG uses a combination of lossy and lossless optimization to reduce filesize of the image asset. Try several JPEG quality levels to find the best quality vs. filesize tradeoff for your asset.

### Delivering scaled image assets

As a result, one of the simplest and most effective image optimization techniques is to ensure that we are not shipping any more pixels than needed to display the asset at its intended size in the browser. Sounds simple, right? Unfortunately, most pages fail this test for many of their image assets: typically, they ship larger assets and rely on the browser to rescale them - which also consumes extra CPU resources - and display them at a lower resolution.

## Testing

### Optimize images

[tinyjpg]
[tinypngpg]

#### Image test scenario 1 (JPG) (Square image)


Original file size: 311 KB |

Original image dimensions: 1440px width 1440px height |

Page speed score (Desktop): 50/100 |


Changes: Lossy and lossless compression + delivering scaled image. Take the needed image size from inspect element and double the width.

For example: 245 x 2 = 490 width

Use photoshop on the original image. Image > Image size. Enter the new width and make sure the height automatically adjusts to scale the image. Use the save for web option. Save out the file at 100% quality with no options selected.

Then use [tinyjpg] to apply lossy and lossless compression on the file.

New file size: 41 KB |

New image dimensions: 490px width 490px height |

Page speed score (Desktop): 51/100 |

#### Image test scenario 2 (JPG) (Long image)


Original file size: 356 KB |

Original image dimensions: 1440px width 2016px height |

Page speed score (Desktop): 51/100 |


Changes: Lossy and lossless compression + delivering scaled image. Take the needed image size from inspect element and double the width and height

For example: 245 x 2 = 490 width
For example: 343 x 2 = 686 height

Use photoshop and create a new file with the dimensions 490px width and 686px height. Drag the original image inside photoshop and scale the image without losing quality in the new dimensions. Use the save for web option. Save out the file at 100% quality with no options selected.

Then use [tinyjpg] to apply lossy and lossless compression on the file.

New file size: 102 KB |

New image dimensions: 490px width 490px height |

Page speed score (Desktop): 53/100 |


#### SCORE OF 96/100 WITHOUT ANY IMAGES BELOW

#### Image test 1000w x 1000h = 525kb

Adding this image https://makeaweb.com.au/images/uploads/os-test-1000x1000.jpg made my PageSpeed go down from 96/100 to 71/100

#### Image test 500w x 500h - no compression = 199kb

Adding this image https://makeaweb.com.au/images/uploads/os-test-500x500.jpg made my PageSpeed go down from 96/100 to 84/100

#### Image test 1000w x 1000h - Compressed to file size of 500 by 500 image = 201kb

Adding this image https://makeaweb.com.au/images/uploads/os-test-1000x1000-compressed.jpg made my PageSpeed go down from 96/100 to 92/100

### Conclusion

Following the test in scenario 1 and 2 will give an improvement to page speed. I followed these methods for 5 images and got an improvement from 50/100 to 60/100. Each image will have different original image dimensions. Optimization of each image should be dealt with individually. Using the [image checklist] will help identify what you should be doing / make sure to use the correct image format for the situation. Lastly always ask yourself the question what value does the image bring. If the image doesn't constitute meaning, what purpose does that image really have?

## Reading

[Google PageSpeed Insights]

[Image Optimization]

[Lossless vs lossy image compression]

[Image compression]

[lossy]

[lossless]

[compression techniques]

[image checklist]

[Google PageSpeed Insights]: https://developers.google.com/speed/pagespeed/insights/
[Image Optimization]: https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization
[Lossless vs lossy image compression]: https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization
[Image compression]:https://en.wikipedia.org/wiki/Image_compression
[lossy]:https://en.wikipedia.org/wiki/Lossy_compression
[lossless]:https://en.wikipedia.org/wiki/Lossless_compression
[compression techniques]:https://developers.google.com/speed/webp/docs/compression
[tinyjpg]:https://tinyjpg.com/
[tinypngpg]:https://tinypng.com/
[image checklist]:/docs/digitalmarketing/2017/09/21/google-page-speed-checks.html
