---
title: "setlocale、_wsetlocale |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c52697fffb27e6fd25936f3c6566f027cc265c18
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="setlocale"></a>setlocale
ワイド文字定数、リテラル文字列を変換するときに使用するロケール (国/地域および言語) を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>コメント  
 マルチバイト文字をワイド文字に変換するアルゴリズムはロケールやコンパイルによって異なる場合や、実行可能ファイルを実行するロケールとは別のロケールでコンパイルされる場合があるため、このプラグマはコンパイル時にターゲットのロケールを指定する方法を提供します。 これによって、ワイド文字列が必ず正しい形式で保存されるようになります。  
  
 既定値*ロケール文字列*は""です。  
  
 "C" ロケールは、文字列の各文字を `wchar_t` (unsigned short) として値にマップします。 その他の値として有効な`setlocale`内にあるエントリです、[言語識別文字列](../c-runtime-library/language-strings.md) ボックスの一覧です。 たとえば、次のように発行します。  
  
```  
#pragma setlocale("dutch")  
```  
  
 言語文字列を発行する機能は、コンピューター上でのコード ページおよび言語 ID のサポートによって異なります。  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)