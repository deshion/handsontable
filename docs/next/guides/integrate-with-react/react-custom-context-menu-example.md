---
title: Custom Context Menu example
metaTitle: Custom contest menu example - Guide - Handsontable Documentation
permalink: /next/react-custom-context-menu-example
canonicalUrl: /react-custom-context-menu-example
---

# Custom context menu - example

An implementation of the `@handsontable/react` component with a custom Context Menu added.

::: example #example1 :react
```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import { HotTable } from '@handsontable/react';
import Handsontable from 'handsontable';

const hotSettings = {
  data: Handsontable.helper.createSpreadsheetData(5, 5),
  colHeaders: true,
  contextMenu: {
    items: {
      'row_above': {
        name: 'Insert row above this one (custom name)'
      },
      'row_below': {},
      'separator': Handsontable.plugins.ContextMenu.SEPARATOR,
      'clear_custom': {
        name: 'Clear all cells (custom)',
        callback: function() {
          this.clear();
        }
      }
    }
  },
  licenseKey: 'non-commercial-and-evaluation'
};

const App = () => {
  return (
    <div>
      <HotTable
        id="hot"
        settings={hotSettings}
      />
    </div>
  )
}

ReactDOM.render(<App />, document.getElementById('example1'));
```