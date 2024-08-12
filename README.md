# React Text Truncator 0.0.6

## Install

```
$ npm install react-text-truncator
```

## Usage

```js
import Truncator from 'react-truncator';

// ...

class Foo extends Component {
  executeOnClick(isExpanded) {
    console.log(isExpanded);
  }

  render() {
    return (
      <Truncator
        /* Default options */
        lines={3}
        more="See more"
        less="See less"
        className="content-css"
        anchorClass="see-more-less-clickable"
        onClick={this.executeOnClick}
        expanded={false}
        width={280}
        truncatedEndingComponent={'... '}
      >
        {text}
      </Truncator>
    );
  }
}
```

## API

| Prop                     | Type                     | Default                    | Description                                                                                                                                                   | Example                                                                                                                       |
| ------------------------ | ------------------------ | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| lines                    | integer, boolean {false} | 3                          | Specifies how many lines of text should be preserved until it gets truncated. `false` and any integer < 1 will result in the text not getting clipped at all. | (`false`, `-1`, `0`), `1`, ...                                                                                                |
| children                 | string, React node       |                            | The text to be truncated. Anything that can be evaluated as text.                                                                                             | `'Some text'`, `<p>Some paragraph <a/>with other text-based inline elements<a></p>`, `<span>Some</span><span>siblings</span>` |
| more                     | string, React node       | 'See more'                 | The text to display in the anchor element to show more.                                                                                                       | `'See more'`, `<span>See more</span>`                                                                                         |
| less                     | string, React node       | 'See less'                 | The text to display in the anchor element to show less.                                                                                                       | `'See less'`, `<span>See less</span>`                                                                                         |
| className                | string                   | ''                         | Class name(s) to add on component content wrapper div.                                                                                                        | `'wrapper-class'`, `'wrapper-class-1 wrapper-class-2'`                                                                        |
| anchorClass              | string                   | 'show-more-less-clickable' | Class name(s) to add to the anchor elements. Should be the name of a css class defined globally by you.                                                       | `'my-anchor-class'`, `'class-1 class-2'`                                                                                      |
| onClick                  | Function                 |                            | Function executed on click on 'Show more' or 'Show less'                                                                                                      | `onClick={this.executeOnClick}`                                                                                               |
| expanded                 | boolean                  | 'false'                    | Control the text to be shown as expanded                                                                                                                      | `expanded={true}`                                                                                                             |
| expandByClick            | boolean                  | 'true'                     | Cancel the default anchor click expand behavior                                                                                                               | `expandByClick={false}`                                                                                                       |
| width                    | number                   | `0`                        | If not `0`, the calculation of the content will be based on this number.                                                                                      |                                                                                                                               |
| keepNewLines             | boolean                  | 'false'                    | Controls the new lines in text to be kept or not. When set to true, only strings can be passed in as children, and not html nodes.                            | `keepNewLines={true}`                                                                                                         |
| truncatedEndingComponent | string                   | '...'                      | Control the text to be shown at the end of short text                                                                                                         | `truncatedEndingComponent={'... '}`                                                                                           |
| onTruncate               | Function                 | undefined                  | Function executed on click on Truncate                                                                                                                        | `onTruncate={() => {alert('Turncated!')}}`                                                                                    |

## Developing

Install development dependencies

```
$ npm install
```

Run tests

```
$ npm test
```

Run code linter

```
$ npm run lint
```

Compile to ES5 from /src to /lib

```
$ npm run compile
```

Storybook usage

```
$ npm run storybook --legacy-peer-deps=true
```
