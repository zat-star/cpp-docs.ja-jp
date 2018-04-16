---
title: "LIB の入力ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fea7a8700eb2f5a5deee7afd05af8b0de0e4e71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lib-input-files"></a>LIB の入力ファイル
LIB で想定されている入力ファイルは、次の表に示すように、モードによって異なります。  
  
|モード|入力|  
|----------|-----------|  
|既定値 (構築またはライブラリの変更)|COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット omf オブジェクト モデルの形式 (です) のオブジェクト (.obj) ファイル|  
|/EXTRACT を持つメンバーを抽出します。|COFF ライブラリ (.lib)|  
|ファイルの構築では、エクスポートとインポート ライブラリ/DEF の|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット OMF オブジェクト (.obj) ファイル|  
  
> [!NOTE]
>  LIB の 16 ビット バージョンで作成した OMF ライブラリは、LIB の 32 ビット バージョンへの入力として使用できません。  
  
## <a name="see-also"></a>参照  
 [LIB の概要](../../build/reference/overview-of-lib.md)