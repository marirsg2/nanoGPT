

model.py line 183 
for block in self.transformer.h:
            x = block(x) #THIS is where we would capture the data for the various layers, Tensors in middle layer, less entropy, ? (unsure) at different temperatures too ?
        x = self.transformer.ln_f(x)

HERE catch the embedding in a ALL blocks, over all token gen length. 
STORE IT in numpy array pickle file. (use GPT)
SEE IF YOU ARE RIGHT
USE SIMPLER PROMPTS and see if that reduces the "variance in values" over time for:
    1) same position
    2) UNLIKELY !! because MLP in each block is Nonlinear xform: difference between two block verticle levels. Difference could be any, we just
    want to check if the values have changed significantly. use L2, 
    3) difference across two token positions. NO usE COSInE similarity.
    LATER ONLY - check cosine sim of value vectors !!