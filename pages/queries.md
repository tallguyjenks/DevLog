---
title: Queries
---

- **On going Tasks** {{query (todo todo now later doing)}}
-
  #+BEGIN_QUERY
  {:title "Documentation Inline Tags"
     :query [:find (pull ?b [*])
         :where
         [?b :block/ref-pages ?p]
         [?p :page/name "documentation"]
     ]
  }
  #+END_QUERY
-
-