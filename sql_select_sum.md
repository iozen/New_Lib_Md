SELECT SUM(`time-l`), `user-id` FROM `time-element` GROUP BY `user-id` ORDER BY SUM(`time-l`)
