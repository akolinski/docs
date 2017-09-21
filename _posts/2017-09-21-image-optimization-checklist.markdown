---
layout: post
title:  "Image optimization checklist"
date:   2017-09-21 09:01:00 +1000
categories: digitalmarketing
url: image-optimization-checklist
---

The purpose of this checklist is to help when optimizing your images. Please refer to the original documentation from Google [Image Optimization].

## Checklist

Image optimization is both an art and a science: an art because there is no one definitive answer for how to best compress an individual image, and a science because there are well-developed techniques and algorithms that can help significantly reduce the size of an image.

Some tips and techniques to keep in mind as you work on optimizing your images:

- Prefer vector formats: vector images are resolution and scale independent, which makes them a perfect fit for the multi-device and high-resolution world.

- Minify and compress SVG assets: XML markup produced by most drawing applications often contains unnecessary metadata which can be removed; ensure that your servers are configured to apply GZIP compression for SVG assets.

- Pick best raster image format: determine your functional requirements and select the one that suits each particular asset.

- Experiment with optimal quality settings for raster formats: don't be afraid to dial down the "quality" settings, the results are often very good and byte savings are significant.

- Remove unnecessary image metadata: many raster images contain unnecessary metadata about the asset: geo information, camera information, and so on. Use appropriate tools to strip this data.

- Serve scaled images: resize images on the server and ensure that the "display" size is as close as possible to the "natural" size of the image. - Pay close to attention to large images in particular, as they account for largest overhead when resized!
Automate, automate, automate: invest into automated tools and infrastructure that will ensure that all of your image assets are always optimized.

## Reading

[Image Optimization]

[Image Optimization]: https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization
