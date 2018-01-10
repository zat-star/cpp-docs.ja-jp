---
title: "ANSI C 準拠 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Ansi
dev_langs: C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f9c8831ef19e14d5d65ae39abde9af8ed669bb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ansi-c-compliance"></a>ANSI C 準拠
ランタイム システムのすべての Microsoft 固有の識別子 (関数、マクロ、定数、変数、型の定義など) の名前付け規則は、ANSI に準拠しています。 このドキュメントでは、ANSI/ISO C 標準に従うランタイム関数は、いずれも ANSI 互換であることが記載されています。 ANSI 準拠アプリケーションでは、これらの ANSI 互換の関数だけを使用してください。  
  
 Microsoft 固有の関数とグローバル変数の名前は、1 つのアンダースコアで始まります。 これらの名前は、ローカルでのみ、コードのスコープ内で上書きできます。 たとえば、Microsoft ランタイム ヘッダー ファイルをインクルードするとき、`_open` という名前の Microsoft 固有の関数を、同じ名前のローカル変数を宣言することで上書きできます。 ただし、独自のグローバル関数またはグローバル変数としてこの名前を使用することはできません。  
  
 Microsoft 固有のマクロとマニフェスト定数の名前は、2 つのアンダー スコア、または先頭の 1 つのアンダースコアとその直後の大文字で始まります。 これらの識別子のスコープは絶対です。 たとえば、この理由から Microsoft 固有の識別子 **_UPPER** を使用することはできません。  
  
## <a name="see-also"></a>参照  
 [互換性](../c-runtime-library/compatibility.md)