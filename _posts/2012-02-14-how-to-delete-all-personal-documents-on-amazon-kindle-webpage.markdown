---
layout: post
permalink: how-to-delete-all-personal-documents-on-amazon-kindle-webpage
title: Delete all Personal Documents on Amazon Kindle Webpage
categories:
- Hacks
---

Giacomo1871 says:

To delete all items, make a bookmarklet with following code as an address:
`
javascript:(function(){ var v = new RegExp("PersonalDocuments"); if (!v.test(document.URL)) { return false; } {a=document.getElementsByClassName('rowBodyCollapsed');for(var i = 0; i<a.length; i++){Fion.deleteItem('deleteItem_'+a[i].getAttribute('asin'));};return; }})();`

via [Amazon.com: Customer Discussions: Request for feature: Ability to delete multiple personal documents in one operation](http://www.amazon.com/gp/customer-forum/kindle/ref=cm_cd_notf_message?ie=UTF8&cdForum=Fx1D7SY3BVSESG&cdPage=1&cdThread=Tx3TL21USPN128O#MxTRSYJ92SPV3R).
