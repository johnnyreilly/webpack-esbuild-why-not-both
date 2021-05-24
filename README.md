# webpack-esbuild-why-not-both

Builds can be made faster using tools like [esbuild](https://github.com/evanw/esbuild). However, if you're invested in [webpack](https://github.com/webpack/webpack) but would still like to take advantage of speedier builds, there is a way. This post takes us through using esbuild alongside webpack using the [esbuild-loader](https://github.com/privatenumber/esbuild-loader).

## Web development

With apologies to those suffering from JavaScript fatigue, once again the world of web development is evolving. It's long been common practice to run your JavaScript and TypeScript through some kind of Node.js based build tool, like webpack or rollup.js.  These tools are written in the same language they compile to; JavaScript (or TypeScript). The new kids on the blog are tools like [esbuild](https://github.com/evanw/esbuild), [Vite](https://github.com/vitejs/vite) and [swc](https://github.com/swc-project/swc). The significant difference between these and their predecessors is that they are written in languages like Go and Rust. Go and Rust enjoy far greater performance than JavaScript.  This translates into significantly faster builds. If you'd like to read about esbuild directly there's a [great post](https://blog.logrocket.com/fast-javascript-bundling-with-esbuild/) about it.

These new tools are transformative and represent a likely future of build tooling for the web. In the long term, the likes of esbuild, Vite and friends will likely come to displace the current standard build tools.  So the webpacks, the rollups and so on. 

However, that’s the long term.  There’s a lot of projects out there that are already heavily invested in their current build tooling.  Mostly webpack.  Migrating to a new build tool is no small piece of work.  New projects might start with Vite, but existing ones are less likely to be ported.  There’s a reason webpack is so popular.  It does a lot of things very well indeed. It's battle tested on large projects; it's mature and it handles many use cases.

So if you’re a team that wants to have faster builds, but doesn’t have the time to go through a big migration... Is there anything you can do?  Yes. There’s a middle ground to be explorerd. There’s a relatively new project named [esbuild-loader](https://github.com/privatenumber/esbuild-loader) developed by [hiroki osame](https://twitter.com/privatenumbr). It's a webpack loader built on top of esbuild. It allows users to swap out ts-loader or babel-loader with itself, and massively improve build speeds.

To declare an interest here, I'm the primary maintainer of [ts-loader](https://github.com/TypeStrong/ts-loader); a popular TypeScript loader that is commonly used with webpack. The important thing here is developer productivity. As a node-based projects, ts-loader and babel-loader will never be able to compete with esbuild-loader in the same way. Go really, uh, goes!

Whilst esbuild may not work for all use cases, it will for the majority. As such esbuild-loader represents a middle ground; and an early way to get access to the increased build speed that esbuild offers *without* saying goodbye to webpack.  This post will look at using esbuild-loader in your webpack setup.







The blog post I’m proposing is kind of a longer form of what I’ve just been explaining.  Perhaps it might also include a description of how to migrate to use esbuild-loader from babel-loader or ts-loader.  Maybe an example of customising Create React App to use esbuild-loader with CRACO.  Or similar.



A blog post on using esbuild-loader to speed up your webpack builds
