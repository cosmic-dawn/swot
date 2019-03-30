README file of test/ 
--

This folder include

1. a config file `config_test1.para`
1. an extract from Laigle et al. (2016) catalog `cosmos2015_test1_z05-1.fits`
1. a random catalog `random_test1.fits`
1. the resulting angular correlation function `test1_acf.out_old` to compare
1. the resulting RR file `test1_rr_out_old` to compare

To run this test:

```bash
cd swot/
mpirun -np 8 bin/swot -c test/config_test1.para
```
 
The results are stored in the file `test/test1_acf.out` and 
`test/test1_rr_out`, which should be compared with the 
correspondent `_old` version. The RR file is a binary file
and can be analysed as follow:

```bash
xxd test/test1_rr_out_old > old.hex
xxd test/test1_rr_out > new.hex
diff old.hex new.hex
```

while `test1_acf.out` is an ASCII table and can be directly compared 
with the `diff` command.

