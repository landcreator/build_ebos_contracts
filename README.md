

base_dir= /Users/song/Code/github.com/landcreator

for c in bios system token msig; do cp ${base_dir}/ebos.contracts/build/contracts/eosio.$c/eosio.$c.* ./v1.0.0/ ;done




cp -r ../../ebos.contracts/build/contracts/eosio.* .
song:v1.0.1 (master)$   for d in `ls`; do cd $d && rm -rf CMakeFiles && rm Makefile cmake_install.cmake && cd .. ; done

 