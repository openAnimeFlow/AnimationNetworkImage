# Animation Network Image

一个带有渐变加载动画效果的 Flutter 网络图片组件。

## 简介

AnimationNetworkImage 是一个基于 [cached_network_image](https://pub.dev/packages/cached_network_image) 的 Flutter 组件，提供了以下功能：

- 网络图片加载与缓存
- 图片加载时的渐变闪烁动画效果（Shimmer）
- 加载错误时的占位文本显示
- 可自定义的圆角边框
- 可配置的淡入淡出动画时长

## 功能特点

1. **图片缓存**: 使用 cached_network_image 实现图片缓存，提升二次加载速度
2. **加载动画**: 在图片加载过程中显示流畅的渐变闪烁动画
3. **错误处理**: 提供加载失败时的错误提示
4. **样式定制**: 支持设置图片尺寸、填充模式、圆角等属性
5. **主题适配**: 自动适配深色/浅色主题的加载动画颜色

## 安装

在 `pubspec.yaml` 文件中添加依赖：

```yaml
dependencies:
  animation_network_image:
  git:
    url: https://github.com/openAnimeFlow/AnimationNetworkImage.git
    ref: main
```

然后运行：

```bash
flutter pub get
```

## 使用方法

### 基本使用

```dart
import 'package:animation_network_image/animation_network_image.dart';

AnimationNetworkImage(
  url: 'https://example.com/image.jpg',
)
```

### 自定义参数

```dart
AnimationNetworkImage(
  url: 'https://example.com/image.jpg',
  width: 200,
  height: 200,
  fit: BoxFit.cover,
  borderRadius: BorderRadius.circular(12),
  fadeInDuration: Duration(milliseconds: 300),
  fadeOutDuration: Duration(milliseconds: 200),
)
```

### 参数说明

| 参数 | 类型 | 默认值 | 描述 |
|------|------|--------|------|
| url | String | 必填 | 图片的网络地址 |
| width | double? | null | 图片宽度 |
| height | double? | null | 图片高度 |
| fit | BoxFit? | null | 图片填充模式 |
| borderRadius | BorderRadiusGeometry | BorderRadius.zero | 图片圆角 |
| fadeInDuration | Duration | Duration(milliseconds: 500) | 淡入动画时长 |
| fadeOutDuration | Duration | Duration(milliseconds: 300) | 淡出动画时长 |

## 示例项目

```dart
import 'package:flutter/material.dart';
import 'package:animation_network_image/animation_network_image.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Animation Network Image Demo')),
        body: Center(
          child: AnimationNetworkImage(
            url: 'https://example.com/image.jpg',
            width: 200,
            height: 200,
            fit: BoxFit.cover,
            borderRadius: BorderRadius.circular(12),
          ),
        ),
      ),
    );
  }
}
```

## 依赖项

- [cached_network_image](https://pub.dev/packages/cached_network_image) ^3.4.1

## 许可证

MIT License