# wts17 Atsuya Kobayashi 71643667
#!/usr/bin/python

# -*- coding: utf-8 -*-
# naive bayse classification

import codecs
import re
import math

pos_dict = {} # dictionaly of probability of POS / PROB(W|POS)
neg_dict = {} # dictionaly of probability of NEG / PROB(W|NEG)

for line in codecs.open("positive.prob","r","euc-jp"):
    line = line.rstrip() # remove right side \n
    lis = line.split("\t") # split tab
    pos_dict[lis[0]] = float(lis[1])
    #n += 1
    #print n

for line in codecs.open("negative.prob","r","euc-jp"):
    line = line.rstrip()
    lis = line.split("\t")
    neg_dict[lis[0]] = float(lis[1])

pos_prob = 0 # probabilities
neg_prob = 0

for line in codecs.open("test.txt.chasen","r","euc-jp"):
    line = line.rstrip('\r\n')
    if line == "EOS":  #end of stream
        if pos_prob > neg_prob:
            result = "positive"
        else:
            result = "negative"   
        
        print "positive "+str(100 * pos_prob)+"%\nnegative "+str(100 * neg_prob)+"%\nit is "+result
        
    else:
        lis = line.split("\t")
        if lis[0] in pos_dict:
            pos_prob += math.log(pos_dict[lis[0]])
        else:
            None

        if lis[0] in neg_dict:
            neg_prob += math.log(neg_dict[lis[0]])
        else:
            None

