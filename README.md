# React Email Editor

The excellent drag-n-drop email editor by [Avalanche](https://useavalanche.com/) as a [React.js](http://facebook.github.io/react) *wrapper component*. This is the most powerful and developer friendly visual email builder for your app.


![React Email Editor](https://s3.amazonaws.com/unroll-assets/unrollyoutube.png)

## Installation

The easiest way to use React Email Editor is to install it from NPM and include it in your own React build process.

```
npm install avalanche-email-editor --save
```

## Usage

Require the EmailEditor component and render it with JSX:

```javascript
import React, { useRef } from 'react';
import { render } from 'react-dom'

import EmailEditor from 'avalanche-email-editor';

const App = (props) => {
  const emailEditorRef = useRef(null);

  const exportHtml = () => {
    emailEditorRef.current.editor.exportHtml((data) => {
      const { design, html } = data;
      console.log('exportHtml', html);
    });
  };

  const onLoad = () => {
    // you can load your template here;
    // const templateJson = {};
    // emailEditorRef.current.editor.loadDesign(templateJson);
  };

  return (
    <div>
      <div>
        <button onClick={exportHtml}>Export HTML</button>
      </div>
      
      <EmailEditor
        ref={emailEditorRef}
        onLoad={onLoad}
      />
    </div>
  );
};

render(<App />, document.getElementById('app'))
```

### License

Copyright (c) 2021 Unlayer. [MIT](LICENSE) Licensed.
