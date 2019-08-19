# book_refactor
《重构》 读书笔记

## 待查找原因

package.json
```json
"devDependencies": {
  "@babel/cli": "^7.5.5",
  "@babel/core": "^7.5.5",
  "@babel/node": "^7.5.5",
  "@babel/preset-env": "^7.5.5"
}
```

TODO: 下次安装的时候移除 `@babe/node` 或改成 `babel-node-debug` 包测试

原由是：yarn 安装的时候警告这个包已经包含在 `babel/core` 中

```bash
$ yarn install
yarn install v1.15.2
info No lockfile found.
[1/4] Resolving packages...
warning @babel/node > @babel/polyfill@7.4.4: 🚨 As of Babel 7.4.0, this
package has been deprecated in favor of directly
including core-js/stable (to polyfill ECMAScript
features) and regenerator-runtime/runtime
(needed to use transpiled generator functions):

  > import "core-js/stable";
  > import "regenerator-runtime/runtime";
[2/4] Fetching packages...
info fsevents@1.2.9: The platform "win32" is incompatible with this module.
info "fsevents@1.2.9" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved lockfile.
Done in 38.22s.
```
