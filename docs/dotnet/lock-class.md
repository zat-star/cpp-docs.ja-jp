---
title: "lock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c2f2a8e371803d33a2c42508ec595681ada3bab8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="lock-class"></a>lock クラス
このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するロックの取得を自動化します。  構築時にロックを取得し、リリースを破棄時ロックします。  
  
## <a name="syntax"></a>構文  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>コメント  
 `lock`CLR オブジェクトに対してのみ使用できますが、CLR コードでのみ使用できます。  
  
 ロックのクラスは内部的には、<xref:System.Threading.Monitor>アクセスを同期するためにします。 同期の詳細については、このトピックを参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>参照  
 [ロック](../dotnet/lock.md)   
 [lock のメンバー](../dotnet/lock-members.md)