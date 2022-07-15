---
title: Shopware 6 index all products fast
author: pt1602
type: post
---

Only indexes the stock of product, skips everything else to save all products one time.

```
bin/console dal:refresh:index --skip="theme.indexer","flow.indexer","newsletter_recipient.indexer","customer.indexer","landing_page.indexer","media.indexer","media_folder.indexer","media_folder_configuration.indexer","payment_method.indexer","product_stream.indexer","product_stream_mapping.indexer","rule.indexer","sales_channel.indexer","category.indexer","promotion.exclusion","promotion.indexer","product.inheritance","product.variant-listing","product.child-count","product.search-keyword","product.stream","product.rating-averaget","product.cheapest-price","product.category-denormalizer","product.many-to-many-id-field","product.seo-url","netzp.blogpost.indexer" --use-queue
```
