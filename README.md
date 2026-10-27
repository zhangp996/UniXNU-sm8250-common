# UniXNU-sm8250-common

Shared Qualcomm SM8250 / SM8250-AC (kona) support for UniXNU: Kryo 585 CPU
topology, GICv3 ranges, the 19.2 MHz architectural timer, the UFS 3.0 host and
PHY register blocks, the Adreno 650/GMU/SMMU block and QUPv3 wrapper 0.

`soc.toml` selects `ArmCpu` and `ArmDTPlatform`. A device repository supplies
memory layout, peripherals, component selection, firmware, power policy and
packaging.

| Path | Contents |
| --- | --- |
| `soc.toml` | SoC name, description, hardware source and component selection |
| `dts/sm8250.dtsi` | CPU topology, GICv3, timer, UFS, GPU and QUPv3 register ranges |
| `configs/sm8250.config` | Kernel config fragment applied before the device defconfig |
| `patches/xnu/series` | SoC XNU patches in application order (empty: none needed yet) |
| `kits/` | Shared platform operations, added with the first board that needs them |

Every address is an SM8250 platform fact and is verified against the board's own
device tree before a driver consumes it; the board records that check in its
`porting.toml`.

Build through the [UniXNU CLI](https://unixnu.com/building). Read the
[SoC support steps](https://unixnu.com/porting/soc-support),
[device tree](https://unixnu.com/porting/device-tree) and
[component catalog](https://unixnu.com/reference/components).
