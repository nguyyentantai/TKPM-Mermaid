sequenceDiagram
  participant Customer

  Customer->>+SearchPage: 1:onSearch(author)
  SearchPage->>SearchPage: 1.1:validateSearchCriteria()
  
  alt author entered
    SearchPage->>+Catalog:1.2:searchByAuthor(author)
    Catalog->>+SearchResult: 1.2.1:create()
    SearchResult->>-SearchResultPage: 1.2.1.1:display()
  else author not entered
    SearchPage->>-SearchPage:1.3:displayErrorMessage()
  end