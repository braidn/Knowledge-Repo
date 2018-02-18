# Active Admin

##Index

- If modifications are needed create an `index do ... end` block
- Within the block there needs to be reference to columns: `column :title`
- The reference can be random or the actual property name
- These columns can take a block where extra properties/computations can be defined
  - the item passed into the block is just the item that corresponds to the column