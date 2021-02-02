---
title: Lifespan Visualization
summary: An RStudio waffle plot!
tags:
- Data Visualization
date: "2021-02-02T00:00:00Z"

image:
  preview_only: true

# Optional external URL for project (replaces project detail page).
external_link: ""


links:
- icon: github
  icon_pack: fab
  name: Isabella's Code
  url: https://github.com/isabellabenabaye/life-chart

- icon: github
  icon_pack: fab
  name: My Code
  url: https://github.com/xndrmcw/lifespan_viz
# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

## This is the data visualization project page associated with my blog post, which you can find [here.](https://xndrmcw.netlify.app/post/lifespan_viz/) At the bottom of this page, you can find my code.

<img src="/media/lifespan_viz_photos/life_in_months_final.png" height="60%">

Here's my code! There are some packages that are required that aren't up top - I apologize, things got a little messy. If you're reading this and try it for yourself and something breaks, let me know! I can help.

        #Just to emphasize, this code is 90% Isabella Benabaye's! She's the real hero.
        library(tidyverse)
        library(lubridate)
        library(waffle)
        library(hrbrthemes)
        library(extrafont)
        loadfonts(device = "win", quiet = TRUE)

        # Create the data-----
        life_data <-
        tibble(months = factor(rep(month.abb[1:12], 82), levels=month.abb[1:12])) %>%   ## make months
        slice(5:(n()-8)) %>%  ## remove months in 1996 before my birth month (April)
        tibble(
        age = rep(0:80, each = 12) ## age range: 1-70
        ) %>%
        rowid_to_column("row_name")  ## add column for row number
        life_data <- life_data[seq(dim(life_data)[1],1),]
        ## add the "eras" to be colored in the waffle chart
        life_data <- life_data %>%
        mutate(era = fct_inorder(case_when(row_name < 136 ~ "Childhood - NYC",
                                     row_name < 207 ~ "Middle/High School - NJ",
                                     row_name < 262 ~ "College - MA",
                                     row_name > 263 ~ "Time Left")))
        # Waffle chart-----
        life_in_months <- life_data %>%
        count(era) %>% ## the count of each era is the number of months in that era
        ggplot(aes(fill = era, values = n)) +
        geom_waffle(color = "#F7F7F7", n_rows = 12, size = 1, flip = TRUE) + ## make each row a year/12 months
        scale_fill_manual(name = "",
                    values = c("#219EBC","#023047", "#f28482","#FB8500")) +  ## assign colors to the eras
        coord_equal() +
        theme_ipsum(grid = "") +
        theme(legend.text = element_text(family = "Cooper Lt BT", size = 40),
        plot.background = element_rect(fill = "#F7F7F7", color = "#F7F7F7")) +
        theme_enhance_waffle()

        life_in_months

        # Save the chart
        life_in_months + ggsave("life_in_months.png", device = "png", type = "cairo", width = 15, height = 25, dpi = 300)
