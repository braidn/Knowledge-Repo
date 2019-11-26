# TPC Benchmarks

## Notes

* 'Real life', production like benchmarks around transactions against a DB.
* Benchmarks are centered around an order-entry system (9 total tables).
  1. Creation and delivery of orders.
  1. Recording payments.
  1. Checking status of orders.
  1. Monitoring inventory levels from a warehouse.
* Main _perf metric_: amount of orders fully processed in 1 minute.
* Interestingly a 'warehouse' isn't a table but a column on stock.

## More Info

* [Details page][tpc]

[tpc]: http://www.tpc.org/tpcc/detail.asp
