# Skip confirmation

```
# app/model/<name_model>.rb

before_create :skip_email

def skip_email
  self.skip_confirmation!
end

```
