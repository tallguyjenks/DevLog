## **Meta:**
### [[Queries]]
### [[Templates]]
### [[TODO]] | [[DOING]] | [[DONE]] | [[NOW]] | [[LATER]]
## **Tags:**
### **Emoji tags**
#### #star | Stars
#### #idea | Ideas
#### #documentation | Documentation
### #language
### #library
### #tools
## **Queries:**
### 
#+BEGIN_QUERY
{:title "Documentation Inline Tags"
     :query [:find (pull ?b [*])
         :where
         ;;[?b :block/marker "TODO"]
         [?b :block/ref-pages ?p]
         [?p :page/name "documentation"]
     ]
}
#+END_QUERY
###
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
###
