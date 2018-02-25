---
title: "OpenMP ライブラリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>OpenMP ライブラリ
Visual C の OpenMP ランタイム ライブラリを構成する .lib ファイルについて説明します。  
  
 次のライブラリには、ビジュアルの C++ OpenMP のランタイム ライブラリ関数が含まれます。  
  
|OpenMP のランタイム ライブラリ|特性|  
|------------------------------|---------------------|  
|VCOMP です。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|  
|VCOMPD.LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|  
  
 _DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD のソース コードでは、します。LIB 既定 lib になります。 それ以外の場合、VCOMP です。LIB が使用されます。  
  
 使用することができます[/NODEFAULTLIB (ライブラリの無視)](../../../build/reference/nodefaultlib-ignore-libraries.md)既定 lib を削除して、任意のライブラリで明示的にリンクします。  
  
 OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリにおよび、OpenMP を使用するアプリケーションを配布する必要があります。  
  
## <a name="see-also"></a>参照  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)