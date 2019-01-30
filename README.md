### draft-js
---
https://github.com/facebook/draft-js

```
npm install --save draft-js react react-dom
yarn add draft-js react react-dom

npm install
npm run build
```

```js
import React from 'react';
import ReactDOM from 'react-dom';
import {Editor, EditorState} from 'draft-js';
class MyEditor extends React.Component {
  constructor(props){
    super(props);
    this.state = {editorState: EditorState.createEmpty()};
    this.onChange = (editorState) => this.setState({editorState});
    this.setEditor = (editor) => {
      this.editor = editor;
    };
    this.focusEditor = () => {
      if(this.editor) {
        this.editor.focus();
      }
    };
  }
  componentDidMount(){
    this.focusEditor();
  }
  render(){
    return (
      <div style={styles.editor} onClick={this.focusEditor}>
        <Editor
          ref={this.setEditor}
          editorState={this.state.editorState}
          onChange={this.onChange}
        />
      </div>
    );
  }
}
const styles = {
  editor: {
    border: '1px solid gray',
    minHeight: '6em'
  }
};
ReactDOM.render(
  <MyEditor />,
  document.getElementById('container')
);
```

```
<meta charset="utf-8" />
```


