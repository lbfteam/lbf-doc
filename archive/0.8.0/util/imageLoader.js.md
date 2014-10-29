#util/util.imageLoader

Provide a util for load image and invoke callback
At this moment, we only support one image for a time, but multiple support is coming soon

####Example

     imageLoader('http://xxx.com/img.jpg', function(){
         alert('ok');
     });

