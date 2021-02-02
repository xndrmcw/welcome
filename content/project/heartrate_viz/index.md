---
title: Fitbit HR Visualization
summary: A plotly-generated heartrate visualization!
tags:
- Data Visualization
date: "2021-02-02T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""


links:
- icon: github
  icon_pack: fab
  name: My Code
  url: https://github.com/xndrmcw/heartrate_vis
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

## The graph below is interactive! Mouse over some points to see what my heartrate was, and at what time.

<iframe width="675" height="500" frameborder="0" scrolling="no" src="//plotly.com/~alexandermcw/1.embed"></iframe>

The This is the project page associated with my blog post, found [**here.**](https://xndrmcw.netlify.app/post/heartrate_viz/)

If you'd like, you can read my code below. It's not the prettiest, but I'm getting better, I swear!

        import plotly.express as px
        import pandas as pd
        import plotly.graph_objects as go
        import numpy as np

        # reads in data
        data = pd.read_csv(r"C:\Users\Alexander\Desktop\Fun Programming\catherine_birthday_HR.csv")

        #creates x and y axis of the data in the first and second columns of the df, respectively
        x_axis = list(data.iloc[:, 0])
        y_axis = list(data.iloc[:, 1])
        #Calculates the average bpm of the time period
        average_bpm = np.mean(y_axis)
        # Just a quick print to show that it's working

        pd.set_option('display.max_columns', None)
        print(data.head())

        # creates the initial figure, sets a title, and colors by value, on a continuous scale
        # Agsunset is one of the plotly gradients. can reverse the color by adding '_r' to the end
        figure = px.scatter(data_frame=data, x = x_axis, y = y_axis,
                            title="CATHERINE'S 22ND BIRTHDAY: MY FITBIT HEARTRATE DATA",
                            color = 'Heart Rate', color_continuous_scale='Agsunset')

        # Adds annotations including arrows, pointing to the points in the data that I wanted. X refers to the
        # row # in the data, also the x-axis position, y refers to the y-axis position in the graph
        figure.add_annotation(x=2190, y=163,
                    text="Mile Run",
                    font=dict(color='#dcd0f4',
                              family='Agency FB'),
                    showarrow=True,
                    arrowhead=1,
                    arrowcolor='#dcd0f4')
        figure.add_annotation(x=2635, y=164,
                    text="Hot Tub",
                    font=dict(color='#dcd0f4',
                              family='Agency FB'),
                    showarrow=True,
                    arrowhead=1,
                    arrowcolor='#dcd0f4')


        # First line centers the title. The .5 and center might be redundant. Below, I style the font using
        # hex color, font, and size.
        figure.update_layout(
            title={
                'x':0.5,
                'xanchor': 'center',},
            font=dict(size=20,
                    color='#dcd0f4',
                    family='Agency FB'),
        # This is where I label the x-axis. I didn't want a title, because I thought it was self-explanatory,
        # so i set it to be an empty string. Next, i created a list with the titles of the ticks that i want.
        # tickvals is a list of the x values i want to place the ticktext at.
        # tickangle=0 sets the labels to read horizontally, 90 would be vertical.
            xaxis=dict(
                title='',
                gridcolor = '#bbdefb',
                ticktext=['7 P.M.', '8 P.M.', '9 P.M.', '10 P.M.', '11 P.M.','12 A.M.','1 A.M.', '2 A.M.'],
                tickvals=[0, 426, 800, 1176, 1535, 1894, 2348, 2834],
                tickangle=0,
                tickmode="array",
                tickfont=dict(color='#FA8277',
                              family="Agency FB")
            ),
            yaxis=dict(
                title='',
                gridcolor = '#bbdefb',
                showticklabels=False),
            paper_bgcolor='#464851',
            plot_bgcolor='#464851'
        )

        # Automargin doesn't seem to do anything, i fiddled with the settings. not sure why it's included
        figure.update_xaxes(automargin=True)
        # Fiddling with the size of the points.
        figure.update_traces(mode='markers', marker_size=5.5)
        figure.show()

        figure.write_html("plot.html")
        # uploads the plot to my account on http://chart-studio.plotly.com/
        import chart_studio.plotly as py
        py.plot(figure, filename = 'heartrate_gradient_scatter.py', auto_open=True)
