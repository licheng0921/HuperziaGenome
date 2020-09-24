# Huperzia genome

## Assembly strategy 1: 

## `nextdevono_correct + flye_assembly + nextpolish_polish`

### 1. nextdevono_correct

```shell
## nextdenovo correct raw reads

conda activate python2
mkdir -p /vol3/agis/wangli_group/licheng/huperzia_denovo/nextdenovo_correct
cd /vol3/agis/wangli_group/licheng/huperzia_denovo/nextdenovo_correct

# 1.calculate length cutoff of reads to be corrected
bash 0.seq_stat.sh

# 2.correct read
bash 1.nextdenovo_correct.sh
```



```shell
## merge corrected reads

cd /vol3/agis/wangli_group/licheng/huperzia_denovo/nextdenovo_correct

cat /vol3/agis/wangli_group/licheng/huperzia_denovo/nextdenovo_correct/01_rundir/02.cns_align/01.seed_cns.sh.work/seed_cns*/cns.fasta > /vol3/agis/wangli_group/licheng/huperzia_denovo/nextdenovo_correct/shishan_nextdenovo_correct_subreads_40x.fa
```

---

### 2. flye_assembly

```shell
## flye assembly

mkdir -p /vol3/agis/wangli_group/licheng/huperzia_denovo/flye
cd /vol3/agis/wangli_group/licheng/huperzia_denovo/flye

bash 2.flye_assembly.sh
```

---

### 3. nextpolish_polish

```shell
## nextpolish polish raw contig

mkdir -p /vol3/agis/wangli_group/licheng/huperzia_denovo/flye/40-flyePolish/nextpolish
cd /vol3/agis/wangli_group/licheng/huperzia_denovo/flye/40-flyePolish/nextpolish

bash 3.nextpolish_polish.sh
```



