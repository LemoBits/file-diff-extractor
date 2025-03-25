# DiffPatch

一个用Rust编写的目录比较工具，可以生成可执行的补丁文件。

## Features

- 对比两个目录的文件差异
- 生成可执行的补丁文件（.exe）
- 补丁文件运行时会先验证目标目录是否正确
- 支持指定必要的验证文件，确保补丁应用在正确的目录中
- 支持排除特定后缀名的文件或特定文件夹
- 高效的文件差异提取和应用

## Usage

### Create Patch

```bash
diffpatch create --source <未修改的目录> --target <修改后的目录> --output <补丁文件名> --check-files <验证文件1,验证文件2,...> --exclude-extensions <排除文件后缀名1,排除文件后缀名2,...> --exclude-dirs <排除文件夹1,排除文件夹2,...>
```

#### 排除特定文件或文件夹

可以使用以下参数排除特定类型的文件或特定文件夹：

```bash
# 排除特定后缀名的文件
--exclude-extensions .tmp,.bak,.i64,.psd

# 排除特定文件夹
--exclude-dirs test,build
```

### Apply Patch

将生成的补丁文件放到需要更新的目录中，双击运行即可。补丁程序会先验证目录是否正确，然后应用文件更改。

## Build

```bash
cargo build --release
```

编译后的可执行文件将位于 `target/release/` 目录中。
