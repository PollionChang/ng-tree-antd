# ng-tree-antd

A antd style of based on angular-tree-component.

[![NPM version](https://img.shields.io/npm/v/ng-tree-antd.svg)](https://www.npmjs.com/package/ng-tree-antd)
[![Build Status](https://travis-ci.org/cipchk/ng-tree-antd.svg?branch=master)](https://travis-ci.org/cipchk/ng-tree-antd)

## Demo

[Live Demo](https://cipchk.github.io/ng-tree-antd/)

## Dependencies

+ `angular-tree-component` **^5.0.0**

## Usage & Installation

Install `ng-tree-antd` from `npm`

```
npm install ng-tree-antd --save
```

Import the `NzTreeModule` in to your root `AppModule`.

```
import { NzTreeModule } from 'ng-tree-antd';
import { NgZorroAntdModule } from 'ng-zorro-antd';

@NgModule({
    imports: [BrowserModule, NzTreeModule, NgZorroAntdModule.forRoot()],
    declarations: [AppComponent],
    bootstrap: [AppComponent]
})
export class AppModule { }
```

### Usage

```typescript
import { Component } from '@angular/core';
import { generateData } from './generate-data';

@Component({
  selector: 'demo',
  template: `
  <nz-tree [nzNodes]="nodes"
           [nzOptions]="options"
           (nzEvent)="onEvent($event)"></nz-tree>
  `
})
export class DemoDraggableComponent {
  nodes = [
    {
      name: 'root1'
    },
    {
      name: 'root2'
    },
    {
      name: 'root3'
    },
    {
      name: 'async root4',
      hasChildren: true
    }
  ];

  options = {
    allowDrag: true
  };

  onEvent(ev: any) {
    console.log('onEvent', ev);
  }
}
```

## API

| Name    | Type           | Default  | Summary |
| ------- | ------------- | ----- | ----- |
| nzNodes | `any[]` |  | see [inputs](https://angular2-tree.readme.io/docs/inputs) |
| nzCheckable | `boolean` | `false` | Add a `checkbox` before the node |
| nzShowLine | `boolean` | `false` | Shows a connecting line |
| nzOptions | `TreeOptions` |  | see [options](https://angular2-tree.readme.io/docs/options) |
| nzTitle | `TemplateRef` |  | Custom title |
| nzLoading | `TemplateRef` |  | Custom Loading |
| nzToggleExpanded | `EventEmitter` |  | see [events](https://angular2-tree.readme.io/docs/events) |
| nzActivate | `EventEmitter` |  |  |
| nzDeactivate | `EventEmitter` |  |  |
| nzFocus | `EventEmitter` |  |  |
| nzBlur | `EventEmitter` |  |  |
| nzUpdateData | `EventEmitter` |  |  |
| nzInitialized | `EventEmitter` |  |  |
| nzMoveNode | `EventEmitter` |  |  |
| nzCopyNode | `EventEmitter` |  |  |
| nzLoadNodeChildren | `EventEmitter` |  |  |
| nzChangeFilter | `EventEmitter` |  |  |
| nzEvent | `EventEmitter` |  |  |
| nzStateChange | `EventEmitter` |  |  |
| nzCheck | `EventEmitter` |  | fired `checkbox` is changed |

## Troubleshooting

Please follow this guidelines when reporting bugs and feature requests:

1. Use [GitHub Issues](https://github.com/cipchk/ng-tree-antd/issues) board to report bugs and feature requests (not our email address)
2. Please **always** write steps to reproduce the error. That way we can focus on fixing the bug, not scratching our heads trying to reproduce it.

Thanks for understanding!

### License

The MIT License (see the [LICENSE](https://github.com/cipchk/ng-tree-antd/blob/master/LICENSE) file for the full text)
