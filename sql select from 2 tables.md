SELECT * FROM `product_UA` INNER JOIN `filter_connections` ON product_UA.id = filter_connections.pr_id

SELECT * FROM `product_UA` INNER JOIN `filter_connections` ON product_UA.id = filter_connections.pr_id WHERE filter_connections.data='white' OR filter_connections.data='green'

SELECT * FROM table_1, table_2 WHERE table_1.id > table_2.user_id

SELECT * FROM tranzactions, discord_users WHERE tranzactions.userid2 = discord_users.discord_id OR tranzactions.userid1 = discord_users.discord_id
