---
title: "[HOWTO] Insert widget inside content of CJuiTabs widget in Yii Framework"
date: "2011-04-25"
tags: 
  - "cjuitabs"
  - "php"
  - "web"
  - "yii"
---

**UPDATE:** See the comment from "Mario De Weerd" below. Although it works in the same way, his technique seems more elegant.

I am using Yii PHP Framework 1.1.7 for developing a site. I needed to insert EColorPicker widget inside the content of a tab in CJuiTabs. If $this->widget returned the generated string for embedding a widget, I could use the following code to achieve this:

echo $this->widget('zii.widgets.jui.CJuiTabs', array(
        'tabs' => array(
            'Size' => array('ajax' => array('sizeselection')),
            'Background' => array('content' => $this->widget('application.extensions.colorpicker.EColorPicker',
              array(
                    'name'=>'cp',
                    'mode'=>'textfield',
                    'fade' => false,
                    'slide' => false,
                    'curtain' => true,
                   )
             );),
            //'Colors' => array('ajax' => array('colorselection')),
            'Text' => array('ajax' => array('textselection')),
        ),
        // additional javascript options for the tabs plugin
        'options' => array(
            'collapsible' => true,
        ),
    ));

However, since $this->widget() does not return the string and echoes it instead, I had to do the following to achieve this:

ob\_start();
$this->widget('application.extensions.colorpicker.EColorPicker',
              array(
                    'name'=>'cp',
                    'mode'=>'textfield',
                    'fade' => false,
                    'slide' => false,
                    'curtain' => true,
                   )
             );
$colorPicker = ob\_get\_contents();
ob\_end\_clean();
    $this->widget('zii.widgets.jui.CJuiTabs', array(
        'tabs' => array(
            'Size' => array('ajax' => array('sizeselection')),
            'Background' => array('content' => $colorPicker),
            //'Colors' => array('ajax' => array('colorselection')),
            'Text' => array('ajax' => array('textselection')),
        ),
        // additional javascript options for the tabs plugin
        'options' => array(
            'collapsible' => true,
        ),
    ));

I don't know if it is appropriate to use it like this, but in my case this worked fine.

Hope this helps.
