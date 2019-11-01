# Data and variables




## Data frames

Although this book is a guide to classical inference, we will work with data in a contemporary format. The data we use is organized into *data frames*, which are more-or-less spreadsheets. The columns of the data frame are *variables*, the rows of the data frame are *units of observation*.

As an example, consider data collected by Francis Galton, one of the pioneers of statistics. In the 1880s, seeking to understand genetic inheritance from parent to child, Galton visited almost 200 families in London with both parents living and children who had grown up. Galton recorded the height of the mother and father, and the height and sex of each of the adult children. Figure \@ref{fig:galton-raw} shows part of the data frame.

\begin{table}[t]

\caption{\label{tab:unnamed-chunk-2}Figure 1: The `Galton` data frame containing Galtons measurements of 898 adult children.}
\centering
\begin{tabular}{l|r|r|l|r|r}
\hline
family & father & mother & sex & height & nkids\\
\hline
1 & 78.5 & 67.0 & M & 73.2 & 4\\
\hline
1 & 78.5 & 67.0 & F & 69.2 & 4\\
\hline
1 & 78.5 & 67.0 & F & 69.0 & 4\\
\hline
1 & 78.5 & 67.0 & F & 69.0 & 4\\
\hline
2 & 75.5 & 66.5 & M & 73.5 & 4\\
\hline
2 & 75.5 & 66.5 & M & 72.5 & 4\\
\hline
2 & 75.5 & 66.5 & F & 65.5 & 4\\
\hline
2 & 75.5 & 66.5 & F & 65.5 & 4\\
\hline
3 & 75.0 & 64.0 & M & 71.0 & 2\\
\hline
3 & 75.0 & 64.0 & F & 68.0 & 2\\
\hline
\multicolumn{6}{l}{... and so on for 898 rows altogether.}\\
\end{tabular}
\end{table}

Each row corresponds to a unit of analysis, in this case, a person. The first row is a 6 foot 1.2 inch man, in a family with 4 kids altogether. Looking at the next three rows, you see his three sisters, who are quite tall for the time (5 foot 9 inches) but not as tall as their parents. Their mother was a bit shorter (5 foot 7) and their father was very tall even by today's standards: 6 feet 6.5 inches.

The family is designated with a number. So all four of the first rows are kids in family one, while rows 5 and 6 come from family two.

Most of the variables are *numeric*, as appropriate for height and the number of kids. One variable, `sex`, has values that are labels, M and F here, standing for male and female. Such variables are called *categorical*; the possible labels are the *levels* of the variable. In this book, categorical variables with *two levels* will play a very important role, but certainly there are categorical variables with more than two levels, as we shall see.

The `family` variable has been encoded as a number, but it is not really numerical. For instance, with numbers, 2 is half way between 1 and 3. But family 2 is not "between" families 1 and 2 in any genuinely numerical sense.

## Tabulations

Historically, when data was shared by printing it and when calculations were tedious, data would often be presented as *tabulations*. For instance, one of the very early (Punnet 1905, p. 93) investigations of cross-linkage in genetics examined 799 sweet pea plants, recording the color of the flower and whether the pollen was round or elongated. 

\begin{figure}\includegraphics[width=0.8\linewidth]{images/Punnet-page-93} \caption{Figure 3: Genetics data from 1905}\label{fig:punnet-93}
\end{figure}

This style of presentation is perfectly understandable, but it is not in the modern format for data. As a data table, this would look like:

\begin{table}[t]

\caption{\label{tab:punnet-raw}Figure 4: Punnet's data in a contemporary format}
\centering
\begin{tabular}{l|l|l}
\hline
ID & flower\_color & pollen\_shape\\
\hline
SP2760 & other & long\\
\hline
SP5930 & other & round\\
\hline
SP7510 & white & long\\
\hline
SP5820 & other & round\\
\hline
SP2070 & other & long\\
\hline
SP5350 & other & round\\
\hline
\multicolumn{3}{l}{... and so on for 801 rows altogether.}\\
\end{tabular}
\end{table}

Punnett from Bateson, W., et al. Experimental studies in the physiology of heredity. Reports to the Evolution Committee of the Royal Society 2, 1–55, 80–99 (1905) p. 93.

You may well wonder what benefit there is to working with an 801-row data frame rather than the simple tabulation in the original publication. First, giving the variables names allows us to distinguish between the variable being measured and the level of the measurement. Second, the table makes clear that both variables `flower_color` and `pollen_shape` are categorical. Third, suppose there was some other aspect being recorded about the plants, for instance the plant's height or how much water the plant was given or the name of the technician who recorded the data. Using a data frame, these new variables can easily be added as additional columns. There's no space in the tabulation for these additional measurements.

A fourth reason to prefer the data-frame format for the genetics data is subtle. Most often, you will be using software to analyze data. Storing data in a consistent way -- data frames -- makes it much easier to use standard software than if the data are stored in a (pointless) variety of formats. Even in classical days, the variety of formats used to store data resulted in the creation of "new" statistical methods that were set up to deal with the special format in which data was presented.

## Quantitative and categorical

## Indicator variables

For a categorical variable: is it level X?

## Response and explanatory variables




#### OTHER DATA SETS. Just for my notes. {-}

#### Gosset

`datasets::crimtab`, maybe use dichotimization of data to illustrate other points.

#### Cushny and Peeples

`psych::cushny`

Look at the fractional change in sleep time from control, not the time difference. (There are a lot of people getting very little sleep!)

#### Hooker and Yule

Note on Estimating the Relative Influence of Two Variables upon a Third
Author(s): R. H. Hooker and G. U. Yule
Source: Journal of the Royal Statistical Society, Vol. 69, No. 1 (Mar., 1906), pp. 197-200 Published by: Wiley for the Royal Statistical Society

\begin{figure}\includegraphics[width=0.8\linewidth]{images/india-exports-yule} \caption{Figure 2: Wheat production and export in India, and prices in Britain}\label{yule-exports}
\end{figure}


#### Punnett

Punnett from Bateson, W., et al. Experimental studies in the physiology of heredity. Reports to the Evolution Committee of the Royal Society 2, 1–55, 80–99 (1905)
The following is a summary of the fully recorded plants : (page 93)
Coloured long. Coloured round. White long. White round. 480 144 132 45

Wikipedia and textbooks give these data
Bateson and Punnett experiment
Phenotype and genotype	Observed	Expected from 9:3:3:1 ratio
Purple, long (P_L_)	284	216
Purple, round (P_ll)	21	72
Red, long (ppL_)	21	72
Red, round (ppll)	55	24
