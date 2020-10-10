

base_dir= /Users/song/Code/github.com/landcreator

for c in bios system token msig; do cp ${base_dir}/ebos.contracts/build/contracts/eosio.$c/eosio.$c.* ./v1.0.0/ ;done
