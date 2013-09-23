TouchScrollStageText
====================

An Apache Flex StageText based mobile TextAreaSkin and TextInputSkin that can be used in a Scroller.

TouchScrollStageText provieds a workaround for the StageText floating effect when used in a Scroller.

Currenty in Flex Mobile there are two types of TextInput skins StageText based and non-StageText Based. A discussion of uses for both can be found at: http://help.adobe.com/en_US/flex/mobileapps/WS19f279b149e7481c6a9f451212b87fe7e87-7fff.html

There are many benefits to using the StageText. However currently when using a StageText skin in a Scroller, as would be the case for many forms, the text in the text fied appears to float when scrolling.

TouchScrollStageText is a workaround to the scrolling problem. Modifications have been made to the StyleableStageText class to listen for touch events and position changes to ancestor Scroller components. Because most of the members of the StyleableStageText class are marked private, this cannot be done by simply extending the class. So provided in this package are the TextAreaSkin, TextInputSkin and TextSkinBase classes which have only been modified to use the new TouchScrollStyleableStageText class insead of the original StyleableStageTextclass class.

To use the provided skins simply set the skinClass on a Spark TextArea or TextInput

    <s:TextArea width="100%" skinClass="com.lizardon.touchscrollstagetext.TouchScrollStageTextAreaSkin" text="TouchScrollStageTextAreaSkin"/>
    <s:TextInput width="100%" skinClass="com.lizardon.touchscrollstagetext.TouchScrollStageTextInputSkin" text="TouchScrollStageTextInputSkin"/>

Additionally, because the implementation depends on TouchEvents the Multitouch input mode has to be set to MultitouchInputMode.TOUCH_POINT. This can be done in the Application initializer:

    flash.ui.Multitouch.inputMode = MultitouchInputMode.TOUCH_POINT;

Hopefully Apache will resolve this bug soon and a workaround will not be needed.
