# hls4ml on Alveo U50 (HLS C/C++ Kernel)
## Vitis version 2019.2
## Compile project
```bash
make check TARGET=sw_emu DEVICE=xilinx_u50_xdma_201920_1 all  # software emulation
make check TARGET=hw_emu DEVICE=xilinx_u50_xdma_201920_1 all  # hardware emulation
make TARGET=hw DEVICE=xilinx_u50_xdma_201920_1 all # build
```
## Run project
```bash
XCL_EMULATION_MODE=sw_emu ./host ./build_dir.sw_emu.xilinx_u50_xdma_201920_1/alveo_hls4ml.xclbin  # software emulation
XCL_EMULATION_MODE=hw_emu ./host ./build_dir.hw_emu.xilinx_u50_xdma_201920_1/alveo_hls4ml.xclbin  # hardware emulation
./host alveo_hls4ml.xclbin  # run on U50
```
## Some detail
```bash
This version copies all layers in image-only model.
link: https://github.com/YanLunHuang/alveo_u50_sucess/tree/8_24_pooling_again

I set the precision to ap_fixed<10,6> because the weight data is so big.
The reuse factors in all convolution layers are equal to n_in.
```
