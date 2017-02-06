## James McNellie
### Home Work #1
#### 2/7/2017

#####Maize data
Part 1: Maize data ordered based on increasing position values and with missing data encoded by this symbol: ?

```sh
cut -f1,3,4 snp_position.txt > snp_position_reduced.txt
head -n 1 snp_position_reduced.txt > snp_header.txt
tail -n +2 snp_position_reduced.txt | sort -k1,1 > sorted_snp_position.txt

(head -1 fang_et_al_genotypes.txt; grep -w 'ZMMIL\|ZMMLR\|ZMMMR' fang_et_al_genotypes.txt)> maize_full.txt
cut -f 1,4- maize_full.txt > maize_reduced.txt

awk -f transpose.awk maize_reduced.txt  > transposed_maize.txt

head -n 1 transposed_maize.txt | cut -f 2- > header_maize.txt
tail -n +2 transposed_maize.txt | sort -k1,1 > sorted_t_maize.txt
join -t $'\t' -1 1 -2 1 sorted_snp_position.txt sorted_t_maize.txt > combined_maize.txt

awk '{if ($2 == 1) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr1_pt1.txt
awk '{if ($2 == 2) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr2_pt1.txt
awk '{if ($2 == 3) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr3_pt1.txt
awk '{if ($2 == 4) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr4_pt1.txt
awk '{if ($2 == 5) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr5_pt1.txt
awk '{if ($2 == 6) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr6_pt1.txt
awk '{if ($2 == 7) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr7_pt1.txt
awk '{if ($2 == 8) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr8_pt1.txt
awk '{if ($2 == 9) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr9_pt1.txt
awk '{if ($2 == 10) print $0;}' combined_maize.txt | sort -k3,3n > maize_chr10_pt1.txt
```
Part 2: Maize data ordered based on decreasing position values and with missing data encoded by this symbol: -

```sh
paste combined_maize.txt > combined_maize_sub.txt
sed -ie 's/?/-/g' combined_maize_sub.txt

awk '{if ($2 == 1) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr1_pt2.txt
awk '{if ($2 == 2) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr2_pt2.txt
awk '{if ($2 == 3) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr3_pt2.txt
awk '{if ($2 == 4) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr4_pt2.txt
awk '{if ($2 == 5) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr5_pt2.txt
awk '{if ($2 == 6) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr6_pt2.txt
awk '{if ($2 == 7) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr7_pt2.txt
awk '{if ($2 == 8) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr8_pt2.txt
awk '{if ($2 == 9) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr9_pt2.txt
awk '{if ($2 == 10) print $0;}' combined_maize_sub.txt | sort -k3,3nr > maize_chr10_pt2.txt
```
