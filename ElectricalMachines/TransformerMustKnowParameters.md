
# Parameters of Transformer that we Must know

### 1. Vector Group
vector group of transformer is
1. Dyn11
2. YNd1
3. YNyn0
4. Dyn5
5. Etc....

Here 
- Capital letter is HV winding denotion
- Small letters is LV denotion
- N/n means neutral is brought out i.e., Neutral is available for the connection.
- Number represent the Phase displacement using the [clock method](./Clock_method.md).

#### Dyn11
- D = HV winding is Delta connected.
- y = LV winding is star connected.
- n = Neutral is available on LV side.
- 11 = 30 Degree phase shift / 330 Degree lagging phase shift.

### 2. Transformer Losses

- Loses types
    1. core loss: constant irrespective of Load.
    2. Copper loss: Variable depend on the load.

- If the Transformer run's for only some time then choose the Transformer with less COPPER LOSS.
- If the Transformer run's always with Load choose the Transfprmer with less COPPER LOSS.

### 3. Tap Changers
- In real life we need tap changers because even if we send 230V here the recevier will not receive 230V so to adjust it we use tap changers by controlling the Turns Ratio.
(Vp/Vs)=(Np/Ns)
Vs = Vp*(Ns/Np)

1. Off Load Tap changing: Need to do manuallay after full shutdown.
2. On Load Tap changing: Works Automatic.

### 4. Cooling Method
1. ONAN - Oil Natural Air Natural
2. ONAF - Oil Natural Air Forced
3. OFAF - Oil Forced Air Forced
4. OFWF - Oil Forced Water Forced

Sometimes there are dual rating
Like at 20MW ONAN at 30MW ONAF

### 5. Impedence
- There are multiple impedence options like 2%, 4%, 5%, 10%, 15%, 20%
- When short circuit happens TF with 2% allows more current than TF with 20%

- But we can't choose the one with highest impedence. as it will result in Voltage drop.


