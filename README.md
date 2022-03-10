# Repro for terser return compression issue

Start via

```
npm install
npm run build
npm start
```

then open http://localhost:3000 in Chromium, open DevTools,
locate `input.js` and set a breakpoint on line 2, go to the
Console and run `testFunction()` and click StepOver twice.
In the Sources panel in DevTools it will look like the execution
was paused on `obj.x` property access, but the Console already
shows `1` being logged and the Scope view in the sidebar shows
that the JS engine is really paused on the return position.
