# Blog Site



## Hugo Instructions

To create a new post use the command

```bash
hugo new posts/my-new-post.md
```

Then paste the content of your post into under the metadata header of the resulting file. Next add a `categories` and a `tags` element to the metadata. Set `draft` to false. You will end up with a header that looks like:

```
+++
date = '2025-02-19T19:42:59-06:00'
draft = false
title = 'My New Post'
categories = ["programming"]
tags = ["tag1", "tag2"]
+++
```

To run the hugo server locally, use the `serve.ps1` script. This will delete the public folder and call `hugo serve` to refresh the data. 