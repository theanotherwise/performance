```bash
# High number of TIME_WAIT
sysctl net.ipv4.tcp_max_tw_buckets
sysctl net.core.dev_weight
sysctl net.core.dev_weight_rx_bias
sysctl net.core.netdev_budget
sysctl net.core.netdev_budget_usecs
sysctl net.core.busy_read
sysctl net.core.busy_poll
```

```bash
# safe
sysctl -w net.ipv4.tcp_max_tw_buckets=500000
sysctl -w net.core.dev_weight=128
sysctl -w net.core.dev_weight_rx_bias=32
sysctl -w net.core.netdev_budget=600
sysctl -w net.core.netdev_budget_usecs=8000
sysctl -w net.core.busy_read=50
sysctl -w net.core.busy_poll=50

# bump
sysctl -w net.ipv4.tcp_max_tw_buckets=2000000
sysctl -w net.core.dev_weight=300
sysctl -w net.core.dev_weight_rx_bias=64
```

`netdev_budget` and `netdev_budget_usecs` trade CPU time for backlog drainage under bursty traffic.
`busy_read` and `busy_poll` can reduce latency at the cost of extra CPU burn while sockets are polled.
