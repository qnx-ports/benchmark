# Testing benchmark on QNX

Compile the benchmark source for desired architecture.

**RPI**: Move Benchmark library and the test binary to the target:

e.g.

    - scp ~/benchmark/build/nto-aarch64-le/build/src/libbenchmark* root@<target-ip-address>:/usr/lib
    - scp ~/benchmark/build/nto-aarch64-le/build/test/*test root@<target-ip-address>:/usr/bin
    - scp ~/benchmark/build/nto-aarch64-le/build/lib/lib* root@<target-ip-address>:/usr/lib

ssh into your target and run the tests

**QEMU**: Move Benchmark library and test binary to qemu instance:

e.g.

    - scp ~/benchmark/qnx/build/nto-x86_64-o/build/lib/lib* root@<target-ip-address>:/system/lib
    - scp ~/benchmark/qnx/build/nto-x86_64-o/build/src/libbenchmark* root@<target-ip-address>:/system/lib
    - scp ~/benchmark/qnx/build/nto-x86_64-o/build/test/*test root@<target-ip-address>:/system/xbin

Make sure the library and binary path you're adding to is correct.

ssh into your target and run the tests with the following flags for each test:

- args_product_test --benchmark_min_time=0.01s
- basic_test --benchmark_min_time=0.01s
- benchmark_name_gtest
- benchmark_min_time_flag_iters_test
- benchmark_min_time_flag_time_test
- benchmark_name_gtest
- benchmark_random_interleaving_gtest
- benchmark_setup_teardown_test
- benchmark_test --benchmark_min_time=0.01s
- commandlineflags_gtest
- complexity_test --benchmark_min_time=0.5s
- complexity_test --benchmark_min_time=0.01s
- diagnostics_test --benchmark_min_time=0.01s
- display_aggregates_only_test
- donotoptimize_test --benchmark_min_time=0.01s
- filter_test --benchmark_min_time=0.01s
- filter_test --benchmark_list_tests
- fixture_test --benchmark_min_time=0.01s
- internal_threading_test --benchmark_min_time=0.01s
- link_main_test --benchmark_min_time=0.01s
- map_test --benchmark_min_time=0.01s
- memory_manager_test --benchmark_min_time=0.01s
- min_time_parse_gtest
- multiple_ranges_test --benchmark_min_time=0.01s
- options_test --benchmark_min_time=0.01s
- perf_counters_gtest
- perf_counters_test --benchmark_min_time=0.01s --benchmark_perf_counters=CYCLES,BRANCHES
- register_benchmark_test --benchmark_min_time=0.01s
- repetitions_test --benchmark_min_time=0.01s --benchmark_repetitions=3
- report_aggregates_only_test --benchmark_min_time=0.01s
- reporter_output_test --benchmark_min_time=0.01s
- skip_with_error_test --benchmark_min_time=0.01s
- spec_arg_test --benchmark_filter=BM_NotChosen
- spec_arg_verbosity_test --v=42
- statistics_gtest
- string_util_gtest
- templated_fixture_test --benchmark_min_time=0.01s
- time_unit_gtest
- user_counters_tabular_test --benchmark_counters_tabular=true --benchmark_min_time=0.01s
- user_counters_test --benchmark_min_time=0.01s
- user_counters_thousands_test --benchmark_min_time=0.01s
