# CodeMirror TURTLE Language Support

<span><a href="https://www.npmjs.com/package/codemirror-lang-turtle" title="NPM version badge"><img src="https://img.shields.io/npm/v/codemirror-lang-turtle?color=blue" alt="NPM version badge" /></a></span>

A CodeMirror extension that provides Turtle syntax highlighting and language support.

### Usage

```ts
import { basicSetup } from 'codemirror';
import { EditorView } from '@codemirror/view';
import { EditorState } from '@codemirror/state';
import { turtle } from 'codemirror-lang-turtle';

const doc = `
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix dc: <http://purl.org/dc/elements/1.1/> .
@prefix ex: <http://example.org/stuff/1.0/> .

<http://www.w3.org/TR/rdf-syntax-grammar>
  dc:title "RDF/XML Syntax Specification (Revised)" ;
  ex:editor [
    ex:fullname "Dave Beckett";
    ex:homePage <http://purl.org/net/dajobe/>
  ] .
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