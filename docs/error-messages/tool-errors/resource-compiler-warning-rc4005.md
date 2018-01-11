---
title: "リソース コンパイラの警告 RC4005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC4005
dev_langs: C++
helpviewer_keywords: RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f27de973f0ff18493c182bdf1feb3f2812f39af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4005"></a>リソース コンパイラの警告 RC4005
'identifier': 再定義はマクロ  
  
 識別子が 2 回定義されています。 コンパイラは、2 番目のマクロ定義を使用します。  
  
 この警告は、コマンドラインで、コードでは、マクロを定義することによって生じること、`#define`ディレクティブです。 これにはインクルード ファイルからインポートされたマクロで発生することできます。  
  
 警告をなくすため、削除するいずれかの定義かを使用して、`#undef`ディレクティブを 2 つ目の定義の前にします。