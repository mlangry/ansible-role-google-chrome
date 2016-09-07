mlangry.google-chrome
=========

An Ansible role to install and configure google chrome

Requirements
------------

None.

Role Variables
--------------

````yaml
google_chrome_global_preferences: {}
google_chrome_global_preference_file: /opt/google/chrome/master_preferences
````

Dependencies
------------

None.

Example Playbook
----------------

This role install google chrome web browser.

````yaml
- hosts: all
  roles:
    - mlangry.google-chrome
````

You can set preferences for all users with the variable "google_chrome_global_preferences".

````yaml
google_chrome_global_preferences:
    homepage: http://www.google.com
    homepage_is_newtabpage: false
    browser:
      show_home_button: true
    session:
      restore_on_startup": 4,
      startup_urls:
        - http://www.google.com/ig
    bookmark_bar:
      show_on_all_tabs: true
    extensions:
      settings:
        ealjoljnibpdkocmldliaoojpgdkcdob:
          location: 1
          granted_permissions:
            api:
              - "bookmarks"
              - "tabs"
            explicit_host:
              - "http://*/*"
              - "https://*/*"
          manifest:
            key: "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDGWUFCjyhJGd/Y9lLyku5IYpWbwa7pkWEkcHerFSwLAlLalG9EvRNnAGTbSmjUNjbyO1ZScrPwHJhOcnHLlrcdLxCOEtzrqK882nxi6m4NMbWeYGShjpro3TQooL/nj2W+V+B2bnLUQIAB6YNShNvWtHturEw68vi7xodNcj2FLwIDAQAB"
            name: "Slick RSS"
            permissions:
              - "http://*/"
              - "https://*/"
              - "tabs"
              - "bookmarks"
            update_url: "https://clients2.google.com/service/update2/crx"
            version: "0.0"
          path : "ealjoljnibpdkocmldliaoojpgdkcdob\\0.0"
          state: 1
    browser:
      default_search_provider_data:
        template_url_data:
          alternate_urls: []
          created_by_policy: false
          date_created: '13105789754831161'
          favicon_url: ''
          id: '142'
          image_url: ''
          image_url_post_params: ''
          input_encodings:
            - UTF-8
          instant_url: ''
          instant_url_post_params: ''
          keyword: qwant.com
          last_modified: '13105789754831161'
          new_tab_url: ''
          originating_url: 'https://www.qwant.com/opensearch.xml'
          prepopulate_id: 0
          safe_for_autoreplace: true
          search_terms_replacement_key: ''
          search_url_post_params: ''
          short_name: Qwant
          suggestions_url: 'https://api.qwant.com/api/suggest/?q={searchTerms}&client=opensearch'
          suggestions_url_post_params: ''
          synced_guid: 891E533C-44F3-4FC1-93E4-AD14BD614BE9
          url: 'https://www.qwant.com/?q={searchTerms}&client=opensearch'
          usage_count: 0
````

If you want to import bookmarks:
````yaml
google_chrome_global_bookmarks_file_source: bookmarks.html
google_chrome_global_preferences:
  import_bookmarks_from_file: "/opt/google/chrome/bookmarks.html"

````
The "bookmarks.html" file will be copy to "/opt/google/chrome/bookmarks.html"

For more informations on the preferences file go [here](https://support.google.com/chrome/a/answer/187948?hl=en)

License
-------

MIT
