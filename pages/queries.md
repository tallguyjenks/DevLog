---
title: Queries
---

## **On going Tasks** {{query (todo todo now later doing)}}
## **Waiting Tasks** {{query (todo waiting)}}
## **Templates** {{query (property template) }}
##
#+BEGIN_QUERY
{:title "Languages"
     :query [:find (pull ?pages [*])
         :where
         [?pages :page/properties ?properties]
         [(get ?properties :tags) ?dates]
         [?tags :tag/name ?tag]
         [(contains? #{"language"} ?tag)]
     ]
}
#+END_QUERY
##
