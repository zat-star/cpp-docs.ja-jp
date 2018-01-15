---
title: "OpenMP ライブラリ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c0f009c26789fd771d55dab5fcfe5f342aa03b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="openmp-libraries"></a>OpenMP ライブラリ
Visual C の OpenMP ランタイム ライブラリを構成する .lib ファイルについて説明します。  
  
 次のライブラリには、ビジュアルの C++ OpenMP のランタイム ライブラリ関数が含まれます。  
  
|OpenMP のランタイム ライブラリ|特性|  
|------------------------------|---------------------|  
|VCOMP です。LIB|マルチ スレッド、動的リンク (VCOMP 用インポート ライブラリ。LIB)。|  
|VCOMPD です。LIB|マルチ スレッド、動的リンク (VCOMPD 用インポート ライブラリ。カバー) (デバッグ)|  
  
 _DEBUG がコンパイル時に定義されている場合、 `#include omp.h` VCOMPD のソース コードでは、します。LIB 既定 lib になります。 それ以外の場合、VCOMP です。LIB が使用されます。  
  
 使用することができます[/NODEFAULTLIB (ライブラリの無視)](../../../build/reference/nodefaultlib-ignore-libraries.md)既定 lib を削除して、任意のライブラリで明示的にリンクします。  
  
 OpenMP Dll は、Visual C 再頒布可能パッケージ ディレクトリにおよび、OpenMP を使用するアプリケーションを配布する必要があります。  
  
## <a name="see-also"></a>参照  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)