#ui/ui.widget.ImageViewer

Simple image viewer. When mouse over a element like a text or small image, show a tip that contains detail image.

####Example

     new ImageViewer({
         container: 'someContainerSelector',
         srcElement: 'sourceElementToBePointedTo',
         content: '<div class="wrapper"><img src="" /></div>'
         src: someImageURL,
         direction: 'up',
         margin: 20,
         events: {
             click: function(){
                 alert('click');
             },

             srcChanged: function(){
                 alert('srcChanged');
             },

             justified: function(){
                 alert('justified');
             }
         }
     });

**Extends**: ui.Nodes.Tip

##Properties

###settings

Default settings

**type**: Object

##Methods

###changeSrc

Set image src. Automatically justify image size by calling justify when image loaded

**Chainable**: true

**Params**:  
*   src _String_

    Image src


###justify

Resize image  for proper view

**Chainable**: true

##Events

###loaded

Fire when image is loaded

###justified

Fire when image is justified

