---
layout: post
permalinks: magento-get-products-categories-flat-view
title: Magento - Get All Products with Categories in a Flat View
---


    SELECT 
        w1.website_id,
        w1.name as website_name,
        s1.store_id,
        s1.name as store_name,
        p1.entity_id as product_id,
        p1.sku,
        pname.value as product_name,
        url.value as url_path,
        small_image.value as small_image,
        msrp.value as msrp_price,
        price.value as price,
        p1.created_at as product_created_at,
        p1.updated_at as product_updated_at,
        visibility.value as visibility,
        pstatus.value as status,
        case
            when
                (pstatus.value = 1
                    and visibility.value > 1)
            then
                1
            else 0
        end as enable_flag,
        c1.entity_id as category_id,
        cname.value as category_name,
        c1.parent_id,
        c1.created_at as category_created_at,
        c1.updated_at as category_updated_at
    FROM
        catalog_product_entity p1
            inner join
        eav_attribute p_attr ON p1.entity_type_id = p_attr.entity_type_id
            and p_attr.attribute_code = 'name'
            inner join
        catalog_product_entity_varchar pname ON pname.entity_id = p1.entity_id
            and pname.attribute_id = p_attr.attribute_id
            inner join
        eav_attribute p_attr2 ON p1.entity_type_id = p_attr2.entity_type_id
            and p_attr2.attribute_code = 'url_path'
            inner join
        catalog_product_entity_varchar url ON url.entity_id = p1.entity_id
            and url.attribute_id = p_attr2.attribute_id
            and pname.store_id = url.store_id
            inner join
        eav_attribute p_attr3 ON p1.entity_type_id = p_attr3.entity_type_id
            and p_attr3.attribute_code = 'small_image'
            inner join
        catalog_product_entity_varchar small_image ON small_image.entity_id = p1.entity_id
            and small_image.attribute_id = p_attr3.attribute_id
            and pname.store_id = small_image.store_id
            inner join
        eav_attribute p_attr4 ON p1.entity_type_id = p_attr4.entity_type_id
            and p_attr4.attribute_code = 'msrp'
            inner join
        catalog_product_entity_decimal msrp ON msrp.entity_id = p1.entity_id
            and msrp.attribute_id = p_attr4.attribute_id
            and pname.store_id = msrp.store_id
            inner join
        eav_attribute p_attr5 ON p1.entity_type_id = p_attr5.entity_type_id
            and p_attr5.attribute_code = 'price'
            inner join
        catalog_product_entity_decimal price ON price.entity_id = p1.entity_id
            and price.attribute_id = p_attr5.attribute_id
            and pname.store_id = price.store_id
            inner join
        eav_attribute p_attr6 ON p1.entity_type_id = p_attr6.entity_type_id
            and p_attr6.attribute_code = 'visibility'
            inner join
        catalog_product_entity_int visibility ON visibility.entity_id = p1.entity_id
            and visibility.attribute_id = p_attr6.attribute_id
            and pname.store_id = visibility.store_id
            inner join
        eav_attribute p_attr7 ON p1.entity_type_id = p_attr7.entity_type_id
            and p_attr7.attribute_code = 'status'
            inner join
        catalog_product_entity_int pstatus ON pstatus.entity_id = p1.entity_id
            and pstatus.attribute_id = p_attr7.attribute_id
            and pname.store_id = pstatus.store_id
            inner join
        catalog_category_product ccp ON ccp.product_id = p1.entity_id
            inner join
        catalog_category_entity c1 ON c1.entity_id = ccp.category_id
            inner join
        eav_attribute c_attr ON c1.entity_type_id = c_attr.entity_type_id
            and c_attr.attribute_code = 'name'
            inner join
        catalog_category_entity_varchar cname ON cname.entity_id = c1.entity_id
            and cname.attribute_id = c_attr.attribute_id
            and pname.store_id = cname.store_id
            inner join
        catalog_category_product_index store1 ON store1.product_id = p1.entity_id
            and store1.category_id = c1.entity_id
            inner join
        core_store s1 ON store1.store_id = s1.store_id
            inner join
        core_website w1 ON s1.website_id = w1.website_id



