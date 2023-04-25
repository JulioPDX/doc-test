
# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed |
| ----------- | ------------------ | ------------------ |
| 72 | 72 | 0 |

### Summary Totals Devices Under Tests

| DUT | Total Tests | Tests Passed | Tests Failed | Categories Failed |
| --- | ----------- | ------------ | ------------ | ----------------- |
| CaravanCI1 |  36 | 36 | 0 | IP Reachability |
| CaravanCI2 |  36 | 36 | 0 | IP Reachability |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed |
| ------------- | ----------- | ------------ | ------------ |
| NTP |  3 | 3 | 0 |
| Interface State |  37 | 37 | 0 |
| LLDP Topology |  8 | 8 | 0 |
| MLAG |  2 | 2 | 0 |
| IP Reachability |  12 | 12 | 0 |
| BGP |  21 | 21 | 0 |
| Routing Table |  8 | 8 | 0 |

## All Test Results

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | CaravanCI1 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 2 | CaravanCI2 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 4 | CaravanCI1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 | PASS | - |
| 10 | CaravanCI2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 | PASS | - |
| 51 | CaravanCI1 | IP Reachability | ip reachability test links | Source: CaravanCI1_Ethernet1 - Destination: CaravanCI2_Ethernet1 | PASS | - |
| 59 | CaravanCI1 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 60 | CaravanCI2 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 62 | CaravanCI1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 142.215.226.188 | PASS | - |
| 65 | CaravanCI2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 155.204.132.252 | PASS | - |
