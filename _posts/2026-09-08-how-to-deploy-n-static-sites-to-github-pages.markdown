---
layout: post
title:  "How to deploy multiple static sites to github pages"
date:   2026-09-08 20:33:10 -0600
categories: tech
---
First have a web site where you set the DNS and CNAMEs

then create a github repo

then at the root of the repo, create a CNAME file

in github deploy from branch and choose main branch

github should automatically deploy, the dns check should pass. We can then repeat these steps infinitely allowing us to build micro frontends in any language
