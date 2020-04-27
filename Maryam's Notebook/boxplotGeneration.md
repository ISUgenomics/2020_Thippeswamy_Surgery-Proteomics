# Generate boxplots for each signficant protein

* /work/gif/Maryam/projects/Swamy-2020

```
module load r
abund<-read.table("significant-Abundances-all.txt")

```

Create column vectors for each group

```
vehiclenosurgery<-c(1:4)
vehiclesurgery<-c(5:8)
KAnosurgery<-c(9:12)
KAsurgery<-c(13:16)
```



```
system("mkdir boxplots")
system("mkdir boxplots/fixedY")
library(ggplot2)
groups<-c(rep(1,4),rep(2,4),rep(3,4),rep(4,4)) ## create groups

## for loop with fixed range
for (i in seq(1,dim(abund)[1])) {
      ## create the data frame with frequency and group data
      freq<-c(abund[i,])
      df<-as.data.frame(as.matrix(cbind(groups,freq)))
      ## data frame requires that we unlist it or it won't work
      df <- as.data.frame(lapply(df, unlist))
      ## we want the groups to be factors
      df$groups<-as.factor(df$groups)

      ## Generating the file name
      ### Note that `split' is a regexp! If you really want to ##split on a character, use `unlist(strsplit( ))
      Splitfilename <- unlist(strsplit(rownames(abund)[i], " "))
      filename <- Splitfilename[1]

      ## plotting using ggplots gives dynamic control of how we plot it.
      p <- ggplot(df, aes(x=groups, y=freq,  fill=(df$groups))) + geom_boxplot(alpha = 0.4)
      q <- p + stat_summary(fun.y=mean, geom="point", shape=4, size=4)+ geom_jitter(shape=2, position=position_jitter(0.2))+
        scale_x_discrete(labels = c('Vehicle-NoSurgery','Vehicle-Surgery','KA-NoSurgery','KA-Surgery')) +ggtitle(rownames(abund)[i]) +
        theme(plot.title = element_text(hjust = 0.5)) + theme(panel.border = element_blank(), panel.grid.major = element_blank(), panel.grid.minor = element_blank()) + theme(
        panel.background = element_rect(fill = "white", color = "black",size = 0.25, linetype = "solid")) + ylim(17,28) + scale_fill_manual(values = c("#FF4499", "#7C01CD", "#00E2FF","#d8b365"), name = "Groups", labels = c('Vehicle-NoSurgery','Vehicle-Surgery','KA-NoSurgery','KA-Surgery') )

      ## save plot to a file in png and pdf format
      ggsave(paste("boxplots/fixedY/",filename,".png",sep=""), plot = last_plot(), device = "png", path = NULL, scale = 1, width = NA, height = NA, units = c("in", "cm", "mm"), dpi = 300, limitsize = TRUE)
      ggsave(paste("boxplots/fixedY/",filename,".pdf",sep=""), plot = last_plot(), device = "pdf", path = NULL, scale = 1, width = NA, height = NA, units = c("in", "cm", "mm"), dpi = 300, limitsize = TRUE)
}

## for loop with unfixed range for y axis
for (i in seq(1,dim(abund)[1])) {
      ## create the data frame with frequency and group data
      freq<-c(abund[i,])
      df<-as.data.frame(as.matrix(cbind(groups,freq)))
      ## data frame requires that we unlist it or it won't work
      df <- as.data.frame(lapply(df, unlist))
      ## we want the groups to be factors
      df$groups<-as.factor(df$groups)

      ## Generating the file name
      ### Note that `split' is a regexp! If you really want to split on a character, use `unlist(strsplit( ))
      Splitfilename <- unlist(strsplit(rownames(abund)[i], " "))
      filename <- Splitfilename[1]

      ## plotting using ggplots gives dynamic control of how we plot it.
      p <- ggplot(df, aes(x=groups, y=freq),fill=(df$groups))) + geom_boxplot(alpha = 0.5)
      q <- p + stat_summary(fun.y=mean, geom="point", shape=4, size=4)+ geom_jitter(shape=2, position=position_jitter(0.2))+
        scale_x_discrete(labels = c('vehiclenosurgery','vehiclesurgery','KAnosurgery','KAsurgery')) +ggtitle(rownames(abund)[i]) +
        theme(plot.title = element_text(hjust = 0.5)) + theme(panel.border = element_blank(), panel.grid.major = element_blank(), panel.grid.minor = element_blank()) + theme(
        panel.background = element_rect(fill = "white", color = "black",size = 0.25, linetype = "solid")) + + scale_fill_manual(values = c("#FF4499", "#7C01CD", "#00E2FF","#d8b365"), name = "Groups", labels = c('vehiclenosurgery','vehiclesurgery','KAnosurgery','KAsurgery') )

      ## save plot to a file in png and pdf format

      ggsave(paste("boxplots/",filename,".png",sep=""), plot = last_plot(), device = "png", path = NULL, scale = 1, width = NA, height = NA, units = c("in", "cm", "mm"), dpi = 300, limitsize = TRUE)
      ggsave(paste("boxplots/",filename,".pdf",sep=""), plot = last_plot(), device = "pdf", path = NULL, scale = 1, width = NA, height = NA, units = c("in", "cm", "mm"), dpi = 300, limitsize = TRUE)
}

```
