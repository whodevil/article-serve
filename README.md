# article-serve
This is a simple micro service that provides an api for text articles.

## Running

```lein run `pwd`/db```

## Spec

### API
* ```GET article/:id``` - retrieve a specific image.
* ```POST article/:title``` -  create a new text article
    * json ```{ "content" : "", "tag" : []}``` 
* ```GET tag/:tag-name``` - retrieve a list of articles that match the tag.

### Configuration
This app expects as an argument the location of the flat file DB. The database directory is formatted as such:
* ```<database-dir>/db.edn```
* ```<database-dir>/articles/```

#### Example db.edn
```clojure
[{:id 1 
  :title "How emacs changed my workflow"
  :unix-time 1425783619
  :tag [:ranting-computer-nerd :bru-town]}
 {:id 2
  :title "graffiti photos of the day"
  :unix-time 1425785989
  :tag [:art :photography :graffiti]}]
```
