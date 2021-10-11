# BUSCO assessment

---

**a. Create working directionary.**

```shell
mkdir -p /vol3/agis/wangli_group/licheng/huperzia_denovo/flye/40-flyePolish/nextpolish/01_rundir/busco4_plant_new
cd /vol3/agis/wangli_group/licheng/huperzia_denovo/flye/40-flyePolish/nextpolish/01_rundir/busco4_plant_new
```

**b. Run BUSCO.**

`bash run_busco4.sh`

```shell
#!/usr/bin/bash

busco --offline \
	-i /vol3/agis/wangli_group/licheng/huperzia_denovo/flye/40-flyePolish/nextpolish/01_rundir/genome.nextpolish.fasta \
	-l /vol3/agis/wangli_group/licheng/database/busco/viridiplantae_odb10 -o busco -m geno --cpu 20
```





```R
library(ggplot2)

n <- 1:425

f_tab <- as.data.frame(replicate(10000, sample(x = n, size = 71, replace = F)))
w_tab <- as.data.frame(replicate(10000, sample(x = n, size = 110, replace = F)))

len_inter <- c()
for (i in paste('V', 1:10000, sep = '')) {
  len_inter <- c(len_inter, length(intersect(f_tab[,i], w_tab[,i])))
}

hist_tab <- data.frame(len_inter)

ggplot(hist_tab, aes(len_inter)) +
  geom_histogram(binwidth = 1, bin = 100, fill="black",colour="black") +
  geom_vline(aes(xintercept = 53), colour = 'red', linetype = 'dashed') +
  theme_classic() + xlim(0,70) + ylim(0,1200) 
```

