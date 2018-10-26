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


class Article < ActiveRecord::Base
  has_one_attached :asset
end
field :asset, :active_storage

class Article < ActiveRecord::Base
  has_one_attached :asset
  attr_accessor :remove_asset
  after_save { asset.purge if remove_asset == '1' }
end
field :asset, :active_storage do
  delete_method :delete_asset
end
class Article < ActiveRecord::Base
  has_many_attached :assets
  attr_accessor :remove_assets
  after_save do
    Array(remove_assets).each { |id| assets.find_by_id(id).try(:purge) }
  end
end

RailsAdmin.config do |config|
  config.model Player do
    edit do
      field :fans do
        orderable true
      end
    end
  end
end

attr_accessible :fan_ids

config.model Team do
  field :categories do
    inverse_of :teams
  end
end

config.model Team do
  field :players do
    nested_form false
  end
end

config.model Player do
  field :team do
    inline_add false
    inline_edit false
  end
end


```

