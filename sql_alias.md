SELECT SUM(`time-l`) as "sum", `user-id` FROM `time-element` GROUP BY `user-id` ORDER BY SUM(`time-l`)
