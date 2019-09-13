# Reference Implementations for Various Versions of Starkad and Poseidon
This repository contains the source code of reference implementations for various versions of Starkad and Poseidon [1]. Source code is available in both Sage and C++. Moreover, scripts to calculate the round numbers, the round constants, and the MDS matrices are also included.

## *sage_1512_24_x3_bf*
This is an implementation of the Starkad permutation with f(x) = x^3, n = 63, t = 24, N = 1512, and p(x) = x^63 + x + 1.

- Input:
0x2e000000000000005800000000000000a8000000000000014000000000000002600000000000000480000000000000088000000000000010000000000000001e0000000000000038000000000000006800000000000000c000000000000001600000000000000280000000000000048000000000000008000000000000000e00000000000000180000000000000028000000000000004000000000000000600000000000000080000000000000008000000000000000
- Output:
0xd000b39309d3817f002dcb7bad9f2cd9f11e5032542171508f2cff192df03986010e5e7fd650c328155751eae822bac00146420a51d0aec2f368cb8c259f93a1688926778fdf6220387650ff6ecc0805010aaa4bcca523f35c63a79ea8f5717becb60b16159c7f238573aaad5f2302f18779a144205027cd52ff1cfdd84ea58671894a9301ef01a91d9fcc9370f0e804b14f5874686cf30121bbb7abd0bf00afa4e74dc7bc573bdc64be06f5935233e09cd3e71c851609ba8cc6c194d2

## *sage_1518_6_inv_pf*
This is an implementation of the Poseidon permutation with f(x) = x^(-1), n = 253, t = 6, N = 1518, and p = 2^252 + 27742317777372353535851937790883648493.

- Input:
0xa0000000000000000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000000000000000000000000018000000000000000000000000000000000000000000000000000000000000008000000000000000000000000000000000000000000000000000000000000002000000000000000000000000000000000000000000000000000000000000000
- Output:
0x14c0985da9dfcea3ff038828aba85275fce72963a4b9b941557cc547ae965ba4e647aa39894ca86da132e9032764c05e96acd7028dc316d3a37e8243532683e2f36ebebd72f217b64b22db78163a423b9cfc188b63176f5daa39d15fc438b18e69aa1353228c38d9db7008c7249afb3876548969105fddb071b14c360dc9e58fcd7387a7ae11b899c7afddaa46dbbb07be5593409868bda73c9df35d4de3eb572d16807bd46ace6631a1e355e52512372798faf4275571d4a7befef10a6b

## *sage_1536_24_x3_pf*
This is an implementation of the Poseidon implementation with f(x) = x^3, n = 64, t = 24, N = 1536, and p = 2^64 - 2^8 - 1.

- Input:
0x170000000000000016000000000000001500000000000000140000000000000013000000000000001200000000000000110000000000000010000000000000000f000000000000000e000000000000000d000000000000000c000000000000000b000000000000000a0000000000000009000000000000000800000000000000070000000000000006000000000000000500000000000000040000000000000003000000000000000200000000000000010000000000000000
- Output:
0x3035da50ef9485c711fe49ba4e8541bab9ec9ede8ed7013d493f41062e101bbee565eaafcb53d50bba95a0854a6e248e9a5a1f44dd7e1d713bce5405f477ef448ed7837463addf5ee4eb7d9c7a5f9daf7e8128f519834d3db96fabb4f5ca4c886d49b0ff8797b53a1022ff9d05780d408bfd33df7564e4a3a549468c65ac099611347472c385633278e4b89834b9c99a5456ef7f328b6d0de2ddfc23c6b42b8310108d53f4b43126187de621c2cc079abe01dcaa8822159cef40c0836efd8848

## *cpp_1536_24_x3_pf*
This is an implementation of the Sponge function using the Poseidon permutation with f(x) = x^3, n = 64, t = 24, N = 1536, and p = 2^64 - 2^8 - 1.

- Message:
0x424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242424242

- Hash:
0x6a63631044047b981988612d41ea31ccb58ea364b9005f7e8be9806ab0af7576

## *scripts*
- `calc_round_numbers.py`: Calculate round numbers given N, t, M, the field, and the S-box.
- `create_mds_bf.sage`: Create an MDS matrix for Starkad given N and t.
- `create_mds_pf.sage`: Create an MDS matrix for Poseidon given N, t, and a prime number.
- `create_rcs_grain.sage`: Create round constants given the field, the S-box, n, t, R_F, R_P, and (potentially) a prime number in hexadecimal form.

[1] *Starkad and Poseidon: New Hash Functions for Zero Knowledge Proof Systems*. Cryptology ePrint Archive, Report 2019/458. https://eprint.iacr.org/2019/458.