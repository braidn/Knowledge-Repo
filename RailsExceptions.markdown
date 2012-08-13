* When a `raise` statement is used in a model transaction, it automagically forces a rollback of that action.
  * This is handy when dealing with users and deleting the last and final user.