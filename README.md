[WIP] - RailsAdmin Rollincode Sortable Section
--------------------

![screenshort]
(http://i.imgur.com/ndh99X3.jpg)

This section provides the behavior of sortable model in rails_admin.
Jquery UI sortable is used.

All call are done in AJAX

**You have to load sortable gem before rails_admin one.**

In gemfile

````
gem 'rails_admin_sortable', git: 'https://github.com/rollincode/rails_admin_sortable.git'
gem 'rails_admin'
````

Example `config/initializers/rails_admin.rb`

````
config.actions do
    dashboard # mandatory
    index # mandatory
    new

    sortable

    export
    bulk_delete
    show
    edit
    delete


    ## With an audit adapter, you can add:
    #history_index
    #history_show
  end
````

In model config you have to specify your methods

````
sortable do
    label_method 'code'
    position_method 'row_order'
end
````

`label_method` is used for showing the model name (eg: title, etc)

`position_method` is used for the model position method and is **mandatory**

#### TODO ####

- [X] Logic
- [X] Design
- [ ] Test
- [ ] Translation
- [ ] Refactoring
- [ ] Examples + Doc