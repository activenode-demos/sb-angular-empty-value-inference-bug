# sb-angular-empty-value-inference-bug

Steps to reproduce:

1. `npm i`
2. `npm run storybook`
2.1. Go to 'Button/Primary' 
2.2. Click on 'Controls'
2.3. See that label is deactivated and set to `-`
3. Now go to the code file `stories/button.component.ts` and change
```ts
@Input()
  label = '';
```

into 
```ts
@Input()
  label = ' ';
```

(The difference is a space!).
4. Rerun (no hot reload!) `npm run storybook` again and see that the label in Controls section shows as editable label now.