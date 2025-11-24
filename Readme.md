NO MATTER HOW HARD I TRIED I WAS UNABLE TP CRACK THE ROUTING STAGE IN WEEK-7.

I WAS ONLY ABLE TO REDUCE IT TO THIS 

<img width="1920" height="1080" alt="err routing" src="https://github.com/user-attachments/assets/045b681a-beaf-41ba-ac8a-d1cbe924f563" />
this is the config.mk i used

```makefile
export DESIGN_NICKNAME = vsdbabysoc
export DESIGN_NAME     = vsdbabysoc
export PLATFORM        = sky130hd

export vsdbabysoc_DIR = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)

export VERILOG_FILES = $(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/module/vsdbabysoc.v \
                       $(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/module/rvmyth.v \
                       $(DESIGN_HOME)/src/$(DESIGN_NICKNAME)/module/clk_gate.v

export SDC_FILE      = $(DESIGN_HOME)/$(PLATFORM)/$(DESIGN_NICKNAME)/sdc/vsdbabysoc_synthesis.sdc
export VERILOG_INCLUDE_DIRS = $(wildcard $(vsdbabysoc_DIR)/include/)

export ADDITIONAL_LIBS = \
    $(vsdbabysoc_DIR)/lib/avsddac.lib \
    $(vsdbabysoc_DIR)/lib/avsdpll.lib

export ADDITIONAL_GDS  = $(wildcard $(vsdbabysoc_DIR)/gds/*.gds)
export ADDITIONAL_LEFS = $(wildcard $(vsdbabysoc_DIR)/lef/*.lef)

export ADDITIONAL_ROUTING_BLOCKAGES = $(wildcard $(vsdbabysoc_DIR)/route_blockages.tcl)

export CLOCK_PORT = CLK
export CLOCK_NET  = CLK

export FP_PIN_ORDER_CFG = $(wildcard $(vsdbabysoc_DIR)/pin_order.cfg)

export DIE_AREA  = 0   0   1600 1600
export CORE_AREA = 20  20  1580 1580

export FP_CORE_UTIL    = 40
export PLACE_DENSITY   = 0.20

export MACRO_PLACE_HALO    = 40 40
export MACRO_PLACE_CHANNEL = 40 40

export RTLMP_FLOW = 0
export MACRO_PLACEMENT =$(wildcard $(vsdbabysoc_DIR)/macro.cfg)

export CTS_BUF_DISTANCE  = 600
export SKIP_GATE_CLONING = 1

# ----- ROUTING / CONGESTION -----
export GRT_ALLOW_CONGESTION      = 1
export GRT_SKIP_CONGESTION_CHECK = 0
export GRT_CONGESTION_DRIVEN     = 1
export GRT_MAX_ITERATIONS        = 700
export GRT_ADJUSTMENT            = 0.15
export GRT_LAYER_ADJUSTMENTS     = {met1:0.25,met2:0.20,met3:0.15,met4:0.10,met5:0.05}
export GRT_VIA_COST_ADJUSTMENT   = 3.0
export GRT_MAX_TIME              = 3600

# ---- Required for your flow ----
export GRT_FAIL_ON_OVERFLOW = 0
export GRT_OVERFLOW_ITERS   = 50

export TNS_END_PERCENT      = 100
export REMOVE_ABC_BUFFERS   = 1
export MAGIC_ZEROIZE_ORIGIN = 0
export MAGIC_EXT_USE_GDS    = 1

export SPEF_OUTPUT_FILE =$(wildcard $(vsdbabysoc_DIR)/vsdbabysoc.spef)
```

SORRY FOR THE INCONVEVIENCE CAUSED BUT I WILL GET BACK TO IT AND TRY TO RECTIFY IT AS SOON AS POSSIBLE
