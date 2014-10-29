#ui/ui.Nodes.Slider

Base slider component

####Example

   var slider = new Slider({
        //slector: null,
        container: '#container-lbf-slider-horizontal',
        step: 100,
        max: 10000,
        min: 5000,
        orientation: 'horizontal',
        range: true,
        events: {
            load: function(){
                console.log('load');
            },
            beforeSlide: function(e, slide){
                //console('beforeSlide');
            },
            slide: function(e, slider){
                $('#container-lbf-slider-horizontal-val').html(slider.val()[0] + ' - ' + slider.val()[1]);
            },
            afterSlide: function(e, slide){
                //console('afterSlide');
            },
            unload: function(){
                console.log('unload')
            }
        }
    });
    slider.val([6000, 9000]);
    slider.remove();

**Extends**: ui.Nodes.Node

##Properties

###elements

Nodes default UI element，this.$element

**type**: Object

###settings

Default settings

**type**: Object

##Methods

###render

Render panel and initialize events and elements

**Chainable**: true

###_initHandles

init handles

**Chainable**: true

###val

get value

**Chainable**: true

###_val

get value

**Chainable**: true

###_vals

get value

**Chainable**: true

###disable

disable slider

**Chainable**: true

###enable

enable slider

**Chainable**: true

###remove

Remove state

**Chainable**: true

