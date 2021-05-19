## **Meta:**
### [[Queries]]
### [[Templates]]
### [[TODO]] | [[DOING]] | [[DONE]] | [[NOW]] | [[LATER]]
## **Tags:**
### **Emoji tags**
#### #star
#### #idea
### #language
### #library
### #tools
### #documentation
## @@html: <div style="display:none">@@
#+BEGIN_QUERY
{:title "Recent"
 :query [:find (pull ?p [*])
         :in $ ?start
         :where
         [?p :page/last-modified-at ?d]
         [?p :page/name ?n]
         [(>= ?d ?start)]
         [(not= ?n "contents")]]
 :inputs [:4d-before]
 :view (fn [result]
  (for [p (take 4 (sort-by :page/last-modified-at > result))]
    [:div.ls-block.flex.flex-col.pt-1
      [:div.flex-1.flex-row
        [:div.mr-2.flex.flex-row.items-center
          {:style {:height "24px" :margin-top "0" :float "left"}}
          [:a.block-control.opacity-50.hover:opacity-100
            {:style {:min-width "0" :height "16px" :margin-right "2px"}}
            [:span]]
          [:a
            {:href (str "/page/" (:page/name p))}
            [:span.bullet-container.cursor
              [:span.bullet]]]]
        [:div.flex.relative
          [:div.flex-1.flex-col.relative.block-content
            [:div
              [:span.page-reference
                [:a.page-ref
                  {:href (str "/page/" (:page/name p))}
                  (-> p :page/properties :title)]]]]]]]))}
#+END_QUERY
<style>
.custom-query { margin-top: 0; }
.custom-query .opacity-70 { opacity: 1; }
</style>
##
