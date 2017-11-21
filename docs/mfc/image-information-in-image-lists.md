---
title: "イメージ リストの情報をイメージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80e897ec79314abb2e77864e53d470e72f275a94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="image-information-in-image-lists"></a>イメージ リストのイメージ情報
[CImageList](../mfc/reference/cimagelist-class.md)はイメージ リストの情報を取得する関数の数が含まれています。 [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo)メンバー関数、`IMAGEINFO`イメージとマスク ビットマップ、カラー プレーン数と、ピクセルあたりのビットの数および外接する四角形のハンドルを含む単一のイメージに関する情報を含む構造体イメージ、ビットマップ内のイメージです。 この情報を使用すると、イメージのビットマップを直接操作します。  
  
 [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount)メンバー関数がイメージ リスト内のイメージの数を取得します。  
  
 使用して、イメージとイメージ リスト内のマスクを基にアイコンを作成することができます、[廃止](../mfc/reference/cimagelist-class.md#extracticon)メンバー関数。 関数は、新しいアイコンのハンドルを返します。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

