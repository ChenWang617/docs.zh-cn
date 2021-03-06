---
title: IMetaDataEmit 接口
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c77edfff640f796dd3f345eaeb4728830c5f4c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit 接口
提供创建、 修改和当前定义的范围中保存有关程序集的元数据的方法。 元数据可以存储在内存中或保存到磁盘。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ApplyEditAndContinue 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|使用在指定所做的更改更新当前的程序集范围`pImport`。|  
|[DefineCustomAttribute 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|使用指定的元数据签名，要附加到指定的对象，创建的自定义特性的定义并获取指向该自定义特性定义的标记。|  
|[DefineEvent 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|使用指定的元数据签名中，创建事件的定义并获取该事件定义的标记。|  
|[DefineField 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|使用指定的元数据签名中，创建一个字段的定义并获取指向该字段定义的标记。|  
|[DefineImportMember 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|创建可以为当前作用域，外部模块中定义，获取该引用定义的标记的类型成员的定义。|  
|[DefineImportType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|创建定义在当前作用域，外部模块中定义并获取该引用定义的标记的类型的引用。|  
|[DefineMemberRef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|创建引用当前作用域之外的模块成员的定义并获取该引用定义的令牌。|  
|[DefineMethod 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|使用指定的签名中，创建某方法的定义，并将令牌返回到该方法定义。|  
|[DefineMethodImpl 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|创建实现接口，从继承的方法的定义，并返回到该方法实现定义的令牌。|  
|[DefineModuleRef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|创建具有指定名称的模块的元数据签名。|  
|[DefineNestedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|创建类型定义的元数据签名并返回`mdTypeDef`令牌对于该类型，此外还指定定义的类型所引用的类型的成员`tdEncloser`。|  
|[DefineParam 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|使用指定的签名与指定标记引用的方法创建的参数定义并获取该参数定义的标记。|  
|[DefinePermissionSet 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|创建一个定义为权限集与指定的元数据签名，并获取该权限集定义的标记。|  
|[DefinePinvokeMap 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|设置 PInvoke 签名由指定标记所引用的方法的功能。|  
|[DefineProperty 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|创建指定类型的属性定义具有指定`get`和`set`方法访问器中，并获取指向该属性定义的标记。|  
|[DefineSecurityAttributeSet 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|创建一组安全权限才能将附加到指定的标记所引用的对象。|  
|[DefineTypeDef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|创建公共语言运行时类型的类型定义并获取该类型定义的元数据标记。|  
|[DefineTypeRefByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|获取当前范围以外的另一个模块中定义的类型元数据标记。|  
|[DefineUserString 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|获取指定的文字字符串的元数据标记。|  
|[DeleteClassLayout 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|销毁指定标记所引用的类型的类布局元数据签名。|  
|[DeleteFieldMarshal 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|销毁 PInvoke 封送处理指定标记所引用的对象的元数据签名。|  
|[DeletePinvokeMap 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|销毁指定标记所引用的对象的 PInvoke 映射元数据。|  
|[DeleteToken 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|从当前的元数据范围中删除指定的标记。|  
|[GetSaveSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|获取当前范围内的程序集的估计二进制大小。|  
|[GetTokenFromSig 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|获取指定的元数据签名令牌。|  
|[GetTokenFromTypeSpec 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|获取具有指定的元数据签名的类型元数据标记。|  
|[Merge 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|将指定的导入作用域添加到要合并的范围列表。|  
|[MergeEnd 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|合并到当前作用域指定一个或多个之前调用的所有元数据作用域`IMetaDataEmit::Merge`。|  
|[Save 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|将所有元数据保存在当前范围内指定地址处的文件。|  
|[SaveToMemory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|将所有元数据保存到指定的内存区域的当前作用域中。|  
|[SaveToStream 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|将所有元数据保存在当前范围内指定`IStream`。|  
|[SetClassLayout 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|设置或更新由以前调用定义的类型的类布局签名`IMetaDataEmit::DefineTypeDef`。|  
|[SetCustomAttributeValue 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|设置或更新由以前调用定义的自定义属性的值`IMetaDataEmit::DefineCustomAttribute`。|  
|[SetEventProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|设置或更新指定的功能，通过调用定义的事件的`IMetaDataEmit::DefineEvent`。|  
|[SetFieldMarshal 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|设置 PInvoke 封送处理指定的标记所引用的字段、 方法返回或方法参数的信息。|  
|[SetFieldProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|设置或更新指定的字段标记所引用的字段的默认值。|  
|[SetFieldRVA 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|设置指定标记所引用的字段的相对虚拟地址的全局变量值。|  
|[SetHandler 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|设置指定所引用的方法`IUnknown`指针作为令牌重新映射通知回调。|  
|[SetMethodImplFlags 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|设置或更新指定标记所引用的继承的方法实现的元数据签名。|  
|[SetMethodProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|设置或更新的功能，存储在指定的相对虚拟地址，通过调用定义的方法的`IMetaDataEmit::DefineMethod`。|  
|[SetModuleProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|更新对由调用定义的模块引用`IMetaDataEmit::DefineModuleRef`。|  
|[SetParamProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|设置或更改功能的已定义的调用的方法参数`IMetaDataEmit::DefineParam`。|  
|[SetParent 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|建立的指定的成员定义的调用`IMetaDataEmit::DefineMemberRef`，是通过调用定义的指定的类型、 成员`IMetaDataEmit::DefineTypeDef`。|  
|[SetPermissionSetProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|设置或更新功能之前调用定义的权限集的元数据签名`IMetaDataEmit::DefinePermissionSet`。|  
|[SetPinvokeMap 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|设置或更改的方法的 PInvoke 签名功能，通过调用定义`IMetaDataEmit::DefinePinvokeMap`。|  
|[SetPropertyProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|设置存储在通过调用定义的属性的元数据的功能`IMetaDataEmit::DefineProperty`。|  
|[SetRVA 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|设置指定的方法的相对虚拟地址。|  
|[SetTypeDefProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|设置由调用定义的类型的功能`IMetaDataEmit::DefineTypeDef`。|  
|[TranslateSigWithScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|将程序集导入当前作用域和为合并的作用域中获取新的元数据签名。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
