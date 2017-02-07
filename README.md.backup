## James McNellie
### Home Work #1
#### 2/7/2017
#### Maize data




Part 1: Maize data ordered based on increasing position values and with missing data encoded by this symbol: ?

```sh
cut -f1,3,4 snp_position.txt > snp_position_reduced.txt
head -n 1 snp_position_reduced.txt > snp_header.txt
tail -n +2 snp_position_reduced.txt | sort -k1,1 > sorted_snp_position.txt

(head -1 fang_et_al_genotypes.txt; grep -w 'ZMMIL\|ZMMLR\|ZMMMR' fang_et_al_genotypes.txt)> maize_full.txt
cut -f 1,4- maize_full.txt > maize_reduced.txt

awk -f transpose.awk maize_reduced.txt  > transposed_maize.txt

head -n 1 transposed_maize.txt | cut -f 2- > header_maize.txt
paste snp_header.txt header_maize.txt > maize_final_header.txt

tail -n +2 transposed_maize.txt | sort -k1,1 > sorted_t_maize.txt
join -t $'\t' -1 1 -2 1 sorted_snp_position.txt sorted_t_maize.txt > combined_maize.txt

 
awk '{if ($2 == 1) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt - > maize_chr1_pt1.txt
awk '{if ($2 == 2) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr2_pt1.txt
awk '{if ($2 == 3) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt - > maize_chr3_pt1.txt
awk '{if ($2 == 4) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr4_pt1.txt
awk '{if ($2 == 5) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr5_pt1.txt
awk '{if ($2 == 6) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr6_pt1.txt
awk '{if ($2 == 7) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr7_pt1.txt
awk '{if ($2 == 8) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr8_pt1.txt
awk '{if ($2 == 9) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr9_pt1.txt
awk '{if ($2 == 10) print $0;}' combined_maize.txt | sort -k3,3n | cat maize_final_header.txt -> maize_chr10_pt1.txt
```
Part 2: Maize data ordered based on decreasing position values and with missing data encoded by this symbol: -

```sh
paste combined_maize.txt > combined_maize_sub.txt
sed -ie 's/?/-/g' combined_maize_sub.txt

awk '{if ($2 == 1) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr1_pt2.txt
awk '{if ($2 == 2) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr2_pt2.txt
awk '{if ($2 == 3) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr3_pt2.txt
awk '{if ($2 == 4) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr4_pt2.txt
awk '{if ($2 == 5) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr5_pt2.txt
awk '{if ($2 == 6) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr6_pt2.txt
awk '{if ($2 == 7) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr7_pt2.txt
awk '{if ($2 == 8) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr8_pt2.txt
awk '{if ($2 == 9) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr9_pt2.txt
awk '{if ($2 == 10) print $0;}' combined_maize_sub.txt | sort -k3,3nr | cat maize_final_header.txt -> maize_chr10_pt2.txt
```
#### Teosinte Data

Part 1: Teosinte data ordered based on increasing position values and with missing data encoded by this symbol: ?

```sh
(head -1 fang_et_al_genotypes.txt; grep -w ‘ZMPBA\|ZMPIL\|ZMPJA' fang_et_al_genotypes.txt) > teosinte_full.txt

cut -f 1,4- teosinte_full.txt > teosinte_reduced.txt

awk -f transpose.awk teosinte_reduced.txt  > transposed_teosinte.txt

head -n 1 transposed_teosinte.txt | cut -f 2- > header_teosinte.txt
paste snp_header.txt header_teosinte.txt > teosinte_final_header.txt

tail -n +2 transposed_teosinte.txt | sort -k1,1 > sorted_t_teosinte.txt
join -t $'\t' -1 1 -2 1 sorted_snp_position.txt sorted_t_teosinte.txt > combined_teosinte.txt

awk '{if ($2 == 1) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr1_pt1.txt
awk '{if ($2 == 2) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr2_pt1.txt
awk '{if ($2 == 3) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr3_pt1.txt
awk '{if ($2 == 4) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr4_pt1.txt
awk '{if ($2 == 5) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr5_pt1.txt
awk '{if ($2 == 6) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr6_pt1.txt
awk '{if ($2 == 7) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr7_pt1.txt
awk '{if ($2 == 8) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr8_pt1.txt
awk '{if ($2 == 9) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr9_pt1.txt
awk '{if ($2 == 10) print $0;}' combined_teosinte.txt | sort -k3,3n | cat teosinte_final_header.txt -> teosinte_chr10_pt1.txt
```

Part 2: Teosinte data ordered based on decreasing position values and with missing data encoded by this symbol: -

```sh
paste combined_teosinte.txt > combined_teosinte_sub.txt
sed -ie 's/?/-/g' combined_teosinte_sub.txt

awk '{if ($2 == 1) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt - > teosinte_chr1_pt2.txt
awk '{if ($2 == 2) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr2_pt2.txt
awk '{if ($2 == 3) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr3_pt2.txt
awk '{if ($2 == 4) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr4_pt2.txt
awk '{if ($2 == 5) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr5_pt2.txt
awk '{if ($2 == 6) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr6_pt2.txt
awk '{if ($2 == 7) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr7_pt2.txt
awk '{if ($2 == 8) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr8_pt2.txt
awk '{if ($2 == 9) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr9_pt2.txt
awk '{if ($2 == 10) print $0;}' combined_teosinte_sub.txt | sort -k3,3nr | cat teosinte_final_header.txt -> teosinte_chr10_pt2.txt
```

