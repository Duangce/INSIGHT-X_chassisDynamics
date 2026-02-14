# :car: 底盘动力学模型集合

本仓库收集并整理了与车辆动力学相关的系统动力学模型与分析资料，主要以 MATLAB/Simulink 仿真模型，是[Insight-X](https://insight-x.xyz) 中底盘动力学的配套文件，可以用学习、快速复现和二次开发。

## 主要目录结构

- `braking/`：制动子模块与参考资料。
- `steer/`：转向相关模型（包含 `sbw_actuator.slx`）。
- `suspension/`：悬架模型集合（2/4/7 自由度模型、Live Script 分析、仿真缓存等）。
- `tire/`：轮胎建模与 Magic Formula 拟合脚本及轮胎数据（CSV）与绘图示例。
- `vehicle/`：整车模型（2/3 自由度线性模型等）与相关绘图、预编译缓存文件。

## 仓库要点

- 模型格式：多数为 Simulink `.slx` / `.slxc` 文件，部分分析采用 MATLAB Live Script (`.mlx`)。
- 依赖：需要安装 MATLAB（含 Simulink），若使用轮胎拟合脚本可能需要 Optimization Toolbox / Curve Fitting Toolbox 等工具箱。
- 仿真缓存：`slprj/` 下含编译与仿真缓存文件，可忽略于版本控制或在需要时删除以节省空间。

## 如何使用
> 本仓库使用软件： matlab-2025b, carsim-2020
> 考虑到版本问题，另导出了2023a版本的simulink文件，在 `兼容性_matlab-2023a版本文件`

1. 在本地打开 MATLAB/Simulink。将工作目录切换到本仓库根目录。
2. 打开需要的模型文件，例如：`vehicle/linear2DOF.slx` 或 `suspension/suspension4DOF.slx`。
3. 若要查看数据处理或拟合流程，打开对应的 Live Script（`.mlx`），例如 `tire/tire_magicFormula_fit251219.mlx`。
4. 建议在第一次打开模型前清理 `slprj/` 及 `sim/varcache/` 中的缓存（可在 MATLAB 中右键模型 -> Clean，有助于避免兼容性问题）。

## 许可证

本项目采用 MIT 许可证，详见仓库根目录的 `LICENSE` 文件。

