# CodeMirror TURTLE Language Support

<span><a href="https://www.npmjs.com/package/codemirror-lang-turtle" title="NPM version badge"><img src="https://img.shields.io/npm/v/codemirror-lang-turtle?color=blue" alt="NPM version badge" /></a></span>

A CodeMirror extension that provides Turtle syntax highlighting and language support.

## Note
This parser is in a usable state but still have big plans for it. Breaking changes can be expected

### Usage

```ts
import { basicSetup } from 'codemirror';
import { EditorView } from '@codemirror/view';
import { EditorState } from '@codemirror/state';
import { turtle } from 'codemirror-lang-turtle';

const doc = `
 SELECT * WHERE { ?s ?p ?o }
`

new EditorView({
  state: EditorState.create({
    doc,
    extensions: [
      basicSetup,
      turtle(),
    ],
  }),
  parent: document.querySelector('#editor'),
});
```