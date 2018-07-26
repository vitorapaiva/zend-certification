#Date & Time

* Definition
	* Functions that retrieve the date and time from the PHP Server
	* Flexbile Date and Time formatting due to the fact that they are stored as a 64-bit number
	* Functions values reflect locale set on server, as well as special date adjustments like daylight savings, time, leap year
* Runtime configuration
	* date.* Functions are affected by php.ini settings
	* date.default_latitude; date.timezone
* Set of predefined constants available
	* DateTime constants provide standard date formats, in conjunction with a date functione like date()
* DateTime Class (REVISAR)
	* Constants: format(Examples)
		const string DateTime::*
		::COOKIE = 1, d-M-y H:i:s T; Monday, 14-AUG-17 15:52:01 UTC
		::RSS = D, d M Y H:i:s O; MON, 14 AUG 2017 15:52:01+0000
	* Methods: Format(Examples)
		public __construct([[string $time="now", DateTimeZone $timezone = NULL]])

		public DateTime add(DateInterval $interval)

		public DateTime setDate (int $year, int $month, int $day)

	* Static methods: format (OOP-Styles Examples)
		Add a specified amount of time to a datetime object
			public DateTime DateTime::add(DateInterval $interval)
		Return a new datetime object (instantion)
			public DateTime::__construct()([[string $time="now", DateTimeZone $timezone = NULL]])
		Return a datetime object in a specific format
			public static DateTime DateTime::createFromFormat(string $format, string $time [, DateTimeZone $timezone])
		Return a date formatted according to a given format
			public string DateTime::format(string $format)
		Return the difference between two datetime objects
			public DateInterval DateTime::diff(DateTime $datetime2, bool $absolute = false])	public DateTime
		Return the unix timestamp
			public int DateTime::getTimestamp(void)
		Alter the current timestamp
			public DateTime DateTime::modify(string $modify)
	* Each case, the method returns an object on success, false on failure
		$timezone: when set to null, returns the current time
		$format: the parameter must be in a format accepted by date()
		$modify: Date/time string in valid formats (add/subtract)

