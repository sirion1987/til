# Create

```

```

# Add field to table

```
AddFieldNameToTableName
```

# Remove

```
RemoveFieldNameFrom<PluralTableName>
```

# Change

```
ChangePluralTableNameFieldName


class ChangePluralTablenameFieldname < ActiveRecord::Migration[5.1]
  def change
    reversible do |dir|
      change_table :tablename do |t|
        dir.up   { t.change :fieldname, :date }
        dir.down { t.change :fieldname, :datetime }
      end
    end
  end
end
```
