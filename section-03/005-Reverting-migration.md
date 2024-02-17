## Reverting Migration

- If we want to revert a migration we can do it by downgrading the migration

___Example___

- If we want revert migration 0003 from store app we can do it as follows

```bash
python manage.py migrate store 0002
```

___Remeber___

- But the migration did not be deleted rather unapplied

- So if you want te clear the reverted migration we have to do it manually and remove the code change from models

