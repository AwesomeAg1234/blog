A simple markdown blog template with built in SEO and google analytics support and very simple config.

The project uses [Hexo](https://github.com/hexojs/hexo) blog framework, you can check out their official docs for advanced config.
Modify `_config.yml` file with your own info, everything needed is documented there.

Some hexo commands:
```bash
hexo new post "<post name>" # you can change post to another layout if you want
hexo clean && hexo generate # generate the static file
hexo server # run hexo in local environment
```

Quick note : If you want to change the header anchor 'ℬ', you can go to `layout/post.ejs` to change it.
```javascript
async("https://cdn.bootcss.com/anchor-js/1.1.1/anchor.min.js",function(){
        anchors.options = {
          visible: 'hover',
          placement: 'left',
          icon: ℬ // this is the header anchor "unicode" icon
        };
```
Oh, and btw you can also keep drafts and archives.

# Have fun ^_^ 
Peace!