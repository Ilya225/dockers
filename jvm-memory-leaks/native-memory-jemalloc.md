# Install Graphviz
sudo apt-get install graphviz

#Clone jemalloc
git clone https://github.com/jemalloc/jemalloc

# Configurie jemalloc with profiling enabled
```
./configure --enable-prof --enable-stats --enable-debug  --enable-fill
make
make install
```

# Export jemalloc Konfiguration
`export MALLOC_CONF="prof:true,prof_prefix:jeprof.out"`

# Shadow glibc malloc with version from jemalloc
`export LD_PRELOAD=/path/to/libjemalloc.so`

# Start Java Application
`java -jar target/spring-boot-jemalloc-example-0.0.1-SNAPSHOT.jar`

# Stat jeprof 
`jeprof --show_bytes --gif jeprof.*.heap` 

# Analyze generated .heap snapshots and combine to .gif
`jeprof --show_bytes --gif jeprof.*.heap  > app-profiling.gif`