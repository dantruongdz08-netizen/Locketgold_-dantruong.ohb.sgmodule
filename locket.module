var body = $response.body;
if (body) {
    try {
        var obj = JSON.parse(body);
        if (obj && obj.subscriber) {
            var expiresDate = "2099-09-09T09:09:09Z";
            var purchaseDate = "2023-09-09T09:09:09Z";
            var productId = "com.locket.gold.yearly";
            var goldData = {
                "expires_date": expiresDate,
                "purchase_date": purchaseDate,
                "product_identifier": productId,
                "is_sandbox": false,
                "ownership_type": "PURCHASED"
            };
            obj.subscriber.entitlements = obj.subscriber.entitlements || {};
            obj.subscriber.entitlements["gold"] = goldData;
            obj.subscriber.entitlements["Locket Gold"] = goldData;
            obj.subscriber.entitlements["premium"] = goldData;
            obj.subscriber.entitlements["60s_video"] = goldData;
            obj.subscriber.subscriptions = obj.subscriber.subscriptions || {};
            obj.subscriber.subscriptions[productId] = {
                "expires_date": expiresDate,
                "purchase_date": purchaseDate,
                "original_purchase_date": purchaseDate,
                "ownership_type": "PURCHASED",
                "store": "app_store"
            };
        }
        body = JSON.stringify(obj);
    } catch (e) {}
}
$done({ body: body });
