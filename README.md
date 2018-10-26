### rails_admin
---
https://github.com/sferik/rails_admin

```
```

```ruby
class Ball < ActiveRecord::Base
  validates :name, presence: true
  belongs_to :player
  
  rails_admin do
    configure :player do
      label 'Owner of this ball: '
    end
  end
end

```

```ruby
RailsAdmin.config do |config|
  config.main_app_name = ["Cool app", "BackOffice"]
  config.main_app_name = Proc.new { |controller| [ "Cool app", "BackOffice - #{controller.params[:action].try(:titelize)}" ]}
end

rquire 'i18n'
I18n.default_locale = :de

config.attr_accessible_role { :default }
config.attr_accessible_role { _current_user.role.to_sym }
config.label_method << :description
config.browser_validations = false







```

