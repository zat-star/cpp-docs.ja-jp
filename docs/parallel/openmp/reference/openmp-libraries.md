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
ms.openlocfilehash: faac1a2a081a2ce0b02f2008bf3766537557df28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)