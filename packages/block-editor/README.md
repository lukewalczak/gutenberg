# Block Editor

This module allows you to create and use standalone block editors.

## Installation

Install the module

```bash
npm install @wordpress/block-editor --save
```

_This package assumes that your code will run in an **ES2015+** environment. If you're using an environment that has limited or no support for ES2015+ such as lower versions of IE then using [core-js](https://github.com/zloirock/core-js) or [@babel/polyfill](https://babeljs.io/docs/en/next/babel-polyfill) will add support for these methods. Learn more about it in [Babel docs](https://babeljs.io/docs/en/next/caveats)._

## Usage

```js
import {
	BlockEditorProvider,
	BlockList
} from '@wordpress/block-editor';
import { useState } from '@wordpress/element';

function MyEditorComponent () {
	const [ blocks, updateBlocks ] = useState( [] );

	return (
		<BlockEditorProvider
			value={ blocks }
			onInput={ updateBlocks }
			onChange={ updateBlocks }
		>
			<WritingFlow>
				<ObserveTyping>
					<BlockList />
				</ObserveTyping>
			</WritingFlow>
			<Popover.Slot />
		</BlockEditorProvider>
	);
}

// Make sure to load the block editor stylesheets too
// import '@wordpress/components/build-style/style.css';
// import '@wordpress/block-editor/build-style/style.css';
```

In this example, we're instantiating a block editor. A block editor is composed by a `BlockEditorProvider` wrapper component where you passe the current array of blocks and on each change the `onInput` or `onChange` callbacks are called depending on whether the change is considered persistent or not.

Inside `BlockEditorProvider`, you can nest any of the available `@wordpress/block-editor` UI components to build the UI of your editor.

In the example above we're rendering the `BlockList` to show and edit the block list. For instance we could add a custom sidebar and use the `BlockInspector` component to be able to edit the advanced settings for the currently selected block. (See the [API](#API) for the list of all the available components).

In the example above, there's no registered block type, in order to use the block editor successfully make sure to register some block types. For instance, registering the core block types can be done like so:

```js
import { registerCoreBlocks } from '@wordpress/block-library';

registerCoreBlocks();

// Make sure to load the block stylesheets too
// import '@wordpress/block-library/build-style/style.css';
// import '@wordpress/block-library/build-style/editor.css';
// import '@wordpress/block-library/build-style/theme.css';
```

## API

<!-- START TOKEN(Autogenerated API docs) -->

<a name="AlignmentToolbar" href="#AlignmentToolbar">#</a> **AlignmentToolbar**

Undocumented declaration.

<a name="Autocomplete" href="#Autocomplete">#</a> **Autocomplete**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/autocomplete/README.md>

<a name="BlockAlignmentToolbar" href="#BlockAlignmentToolbar">#</a> **BlockAlignmentToolbar**

Undocumented declaration.

<a name="BlockControls" href="#BlockControls">#</a> **BlockControls**

Undocumented declaration.

<a name="BlockEdit" href="#BlockEdit">#</a> **BlockEdit**

Undocumented declaration.

<a name="BlockEditorKeyboardShortcuts" href="#BlockEditorKeyboardShortcuts">#</a> **BlockEditorKeyboardShortcuts**

Undocumented declaration.

<a name="BlockEditorProvider" href="#BlockEditorProvider">#</a> **BlockEditorProvider**

Undocumented declaration.

<a name="BlockFormatControls" href="#BlockFormatControls">#</a> **BlockFormatControls**

Undocumented declaration.

<a name="BlockIcon" href="#BlockIcon">#</a> **BlockIcon**

Undocumented declaration.

<a name="BlockInspector" href="#BlockInspector">#</a> **BlockInspector**

Undocumented declaration.

<a name="BlockList" href="#BlockList">#</a> **BlockList**

Undocumented declaration.

<a name="BlockMover" href="#BlockMover">#</a> **BlockMover**

Undocumented declaration.

<a name="BlockNavigationDropdown" href="#BlockNavigationDropdown">#</a> **BlockNavigationDropdown**

Undocumented declaration.

<a name="BlockPreview" href="#BlockPreview">#</a> **BlockPreview**

BlockPreview renders a preview of a block or array of blocks.

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/block-preview/README.md>

_Parameters_

-   _blocks_ `(Array|Object)`: A block instance (object) or an array of blocks to be previewed.
-   _viewportWidth_ `number`: Width of the preview container in pixels. Controls at what size the blocks will be rendered inside the preview. Default: 700.

_Returns_

-   `WPElement`: Rendered element.

<a name="BlockSelectionClearer" href="#BlockSelectionClearer">#</a> **BlockSelectionClearer**

Undocumented declaration.

<a name="BlockSettingsMenu" href="#BlockSettingsMenu">#</a> **BlockSettingsMenu**

Undocumented declaration.

<a name="BlockTitle" href="#BlockTitle">#</a> **BlockTitle**

Undocumented declaration.

<a name="BlockToolbar" href="#BlockToolbar">#</a> **BlockToolbar**

Undocumented declaration.

<a name="BlockVerticalAlignmentToolbar" href="#BlockVerticalAlignmentToolbar">#</a> **BlockVerticalAlignmentToolbar**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/block-vertical-alignment-toolbar/README.md>

<a name="ButtonBlockerAppender" href="#ButtonBlockerAppender">#</a> **ButtonBlockerAppender**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/button-block-appender/README.md>

<a name="ColorPalette" href="#ColorPalette">#</a> **ColorPalette**

Undocumented declaration.

<a name="ContrastChecker" href="#ContrastChecker">#</a> **ContrastChecker**

Undocumented declaration.

<a name="CopyHandler" href="#CopyHandler">#</a> **CopyHandler**

Undocumented declaration.

<a name="createCustomColorsHOC" href="#createCustomColorsHOC">#</a> **createCustomColorsHOC**

A higher-order component factory for creating a 'withCustomColors' HOC, which handles color logic
for class generation color value, retrieval and color attribute setting.

Use this higher-order component to work with a custom set of colors.

_Usage_

```jsx
const CUSTOM_COLORS = [ { name: 'Red', slug: 'red', color: '#ff0000' }, { name: 'Blue', slug: 'blue', color: '#0000ff' } ];
const withCustomColors = createCustomColorsHOC( CUSTOM_COLORS );
// ...
export default compose(
    withCustomColors( 'backgroundColor', 'borderColor' ),
    MyColorfulComponent,
);
```

_Parameters_

-   _colorsArray_ `Array`: The array of color objects (name, slug, color, etc... ).

_Returns_

-   `Function`: Higher-order component.

<a name="DefaultBlockAppender" href="#DefaultBlockAppender">#</a> **DefaultBlockAppender**

Undocumented declaration.

<a name="FontSizePicker" href="#FontSizePicker">#</a> **FontSizePicker**

Undocumented declaration.

<a name="getColorClassName" href="#getColorClassName">#</a> **getColorClassName**

Returns a class based on the context a color is being used and its slug.

_Parameters_

-   _colorContextName_ `string`: Context/place where color is being used e.g: background, text etc...
-   _colorSlug_ `string`: Slug of the color.

_Returns_

-   `?string`: String with the class corresponding to the color in the provided context. Returns undefined if either colorContextName or colorSlug are not provided.

<a name="getColorObjectByAttributeValues" href="#getColorObjectByAttributeValues">#</a> **getColorObjectByAttributeValues**

Provided an array of color objects as set by the theme or by the editor defaults,
and the values of the defined color or custom color returns a color object describing the color.

_Parameters_

-   _colors_ `Array`: Array of color objects as set by the theme or by the editor defaults.
-   _definedColor_ `?string`: A string containing the color slug.
-   _customColor_ `?string`: A string containing the customColor value.

_Returns_

-   `?Object`: If definedColor is passed and the name is found in colors, the color object exactly as set by the theme or editor defaults is returned. Otherwise, an object that just sets the color is defined.

<a name="getColorObjectByColorValue" href="#getColorObjectByColorValue">#</a> **getColorObjectByColorValue**

Provided an array of color objects as set by the theme or by the editor defaults, and a color value returns the color object matching that value or undefined.

_Parameters_

-   _colors_ `Array`: Array of color objects as set by the theme or by the editor defaults.
-   _colorValue_ `?string`: A string containing the color value.

_Returns_

-   `?Object`: Color object included in the colors array whose color property equals colorValue. Returns undefined if no color object matches this requirement.

<a name="getFontSize" href="#getFontSize">#</a> **getFontSize**

Returns the font size object based on an array of named font sizes and the namedFontSize and customFontSize values.
	If namedFontSize is undefined or not found in fontSizes an object with just the size value based on customFontSize is returned.

_Parameters_

-   _fontSizes_ `Array`: Array of font size objects containing at least the "name" and "size" values as properties.
-   _fontSizeAttribute_ `?string`: Content of the font size attribute (slug).
-   _customFontSizeAttribute_ `?number`: Contents of the custom font size attribute (value).

_Returns_

-   `?string`: If fontSizeAttribute is set and an equal slug is found in fontSizes it returns the font size object for that slug. Otherwise, an object with just the size value based on customFontSize is returned.

<a name="getFontSizeClass" href="#getFontSizeClass">#</a> **getFontSizeClass**

Returns a class based on fontSizeName.

_Parameters_

-   _fontSizeSlug_ `string`: Slug of the fontSize.

_Returns_

-   `string`: String with the class corresponding to the fontSize passed. The class is generated by appending 'has-' followed by fontSizeSlug in kebabCase and ending with '-font-size'.

<a name="InnerBlocks" href="#InnerBlocks">#</a> **InnerBlocks**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/inner-blocks/README.md>

<a name="Inserter" href="#Inserter">#</a> **Inserter**

Undocumented declaration.

<a name="InspectorAdvancedControls" href="#InspectorAdvancedControls">#</a> **InspectorAdvancedControls**

Undocumented declaration.

<a name="InspectorControls" href="#InspectorControls">#</a> **InspectorControls**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/inspector-controls/README.md>

<a name="MediaPlaceholder" href="#MediaPlaceholder">#</a> **MediaPlaceholder**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/media-placeholder/README.md>

<a name="MediaUpload" href="#MediaUpload">#</a> **MediaUpload**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/media-upload/README.md>

<a name="MediaUploadCheck" href="#MediaUploadCheck">#</a> **MediaUploadCheck**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/media-upload/README.md>

<a name="MultiBlocksSwitcher" href="#MultiBlocksSwitcher">#</a> **MultiBlocksSwitcher**

Undocumented declaration.

<a name="MultiSelectScrollIntoView" href="#MultiSelectScrollIntoView">#</a> **MultiSelectScrollIntoView**

Undocumented declaration.

<a name="NavigableToolbar" href="#NavigableToolbar">#</a> **NavigableToolbar**

Undocumented declaration.

<a name="ObserveTyping" href="#ObserveTyping">#</a> **ObserveTyping**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/observe-typing/README.md>

<a name="PanelColorSettings" href="#PanelColorSettings">#</a> **PanelColorSettings**

Undocumented declaration.

<a name="PlainText" href="#PlainText">#</a> **PlainText**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/plain-text/README.md>

<a name="PreserveScrollInReorder" href="#PreserveScrollInReorder">#</a> **PreserveScrollInReorder**

Undocumented declaration.

<a name="RichText" href="#RichText">#</a> **RichText**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/rich-text/README.md>

<a name="RichTextShortcut" href="#RichTextShortcut">#</a> **RichTextShortcut**

Undocumented declaration.

<a name="RichTextToolbarButton" href="#RichTextToolbarButton">#</a> **RichTextToolbarButton**

Undocumented declaration.

<a name="SETTINGS_DEFAULTS" href="#SETTINGS_DEFAULTS">#</a> **SETTINGS_DEFAULTS**

The default editor settings

 alignWide                              boolean       Enable/Disable Wide/Full Alignments
 availableLegacyWidgets                 Array         Array of objects representing the legacy widgets available.
 colors                                 Array         Palette colors
 disableCustomColors                    boolean       Whether or not the custom colors are disabled
 fontSizes                              Array         Available font sizes
 disableCustomFontSizes                 boolean       Whether or not the custom font sizes are disabled
 imageSizes                             Array         Available image sizes
 maxWidth                               number        Max width to constraint resizing
 allowedBlockTypes                      boolean|Array Allowed block types
 hasFixedToolbar                        boolean       Whether or not the editor toolbar is fixed
 hasPermissionsToManageWidgets          boolean       Whether or not the user is able to manage widgets.
 focusMode                              boolean       Whether the focus mode is enabled or not
 styles                                 Array         Editor Styles
 isRTL                                  boolean       Whether the editor is in RTL mode
 bodyPlaceholder                        string        Empty post placeholder
 titlePlaceholder                       string        Empty title placeholder
 codeEditingEnabled                     string        Whether or not the user can switch to the code editor
 showInserterHelpPanel                  boolean       Whether or not the inserter help panel is shown
 **experimentalCanUserUseUnfilteredHTML string        Whether the user should be able to use unfiltered HTML or the HTML should be filtered e.g., to remove elements considered insecure like iframes.
 **experimentalEnableLegacyWidgetBlock  boolean       Whether the user has enabled the Legacy Widget Block
 \_\_experimentalEnableMenuBlock          boolean       Whether the user has enabled the Menu Block

<a name="SkipToSelectedBlock" href="#SkipToSelectedBlock">#</a> **SkipToSelectedBlock**

Undocumented declaration.

<a name="storeConfig" href="#storeConfig">#</a> **storeConfig**

Block editor data store configuration.

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/data/README.md#registerStore>

_Type_

-   `Object` 

<a name="transformStyles" href="#transformStyles">#</a> **transformStyles**

Applies a series of CSS rule transforms to wrap selectors inside a given class and/or rewrite URLs depending on the parameters passed.

_Parameters_

-   _styles_ `Array`: CSS rules.
-   _wrapperClassName_ `string`: Wrapper Class Name.

_Returns_

-   `Array`: converted rules.

<a name="URLInput" href="#URLInput">#</a> **URLInput**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/url-input/README.md>

<a name="URLInputButton" href="#URLInputButton">#</a> **URLInputButton**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/url-input/README.md>

<a name="URLPopover" href="#URLPopover">#</a> **URLPopover**

_Related_

-   <https://github.com/WordPress/gutenberg/blob/master/packages/block-editor/src/components/url-popover/README.md>

<a name="Warning" href="#Warning">#</a> **Warning**

Undocumented declaration.

<a name="withColorContext" href="#withColorContext">#</a> **withColorContext**

Undocumented declaration.

<a name="withColors" href="#withColors">#</a> **withColors**

A higher-order component, which handles color logic for class generation color value, retrieval and color attribute setting.

For use with the default editor/theme color palette.

_Usage_

```jsx
export default compose(
    withColors( 'backgroundColor', { textColor: 'color' } ),
    MyColorfulComponent,
);
```

_Parameters_

-   _colorTypes_ `...(Object|string)`: The arguments can be strings or objects. If the argument is an object, it should contain the color attribute name as key and the color context as value. If the argument is a string the value should be the color attribute name, the color context is computed by applying a kebab case transform to the value. Color context represents the context/place where the color is going to be used. The class name of the color is generated using 'has' followed by the color name and ending with the color context all in kebab case e.g: has-green-background-color.

_Returns_

-   `Function`: Higher-order component.

<a name="withFontSizes" href="#withFontSizes">#</a> **withFontSizes**

Higher-order component, which handles font size logic for class generation,
font size value retrieval, and font size change handling.

_Parameters_

-   _fontSizeNames_ `...(Object|string)`: The arguments should all be strings. Each string contains the font size attribute name e.g: 'fontSize'.

_Returns_

-   `Function`: Higher-order component.

<a name="WritingFlow" href="#WritingFlow">#</a> **WritingFlow**

Undocumented declaration.


<!-- END TOKEN(Autogenerated API docs) -->

<br/><br/><p align="center"><img src="https://s.w.org/style/images/codeispoetry.png?1" alt="Code is Poetry." /></p>
