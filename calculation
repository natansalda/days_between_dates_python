def isLeapYear(year):
    if year % 400 == 0:
        return True
    if year % 100 == 0:
        return False
    if year % 4 == 0:
        return True
    else:
        return False
    
def daysInMonth(year, month):
    if month == 1 or month == 3 or month ==5 or month == 7 or month == 8 or month == 10 or month == 12:
        return 31
    else:
        if month == 2:
            if isLeapYear(year):
                return 29
            else:
                return 28
        else:
            return 30

def nextDay(year, month, day):
    """Simple version: assume every month has 30 days"""
    
    if day < daysInMonth(year, month):
        return year, month, day + 1
    else:
        if month == 12:
            return year + 1, 1, 1
        else:
            return year, month + 1, 1
        
def dayIsBefore(y1, m1, d1, y2, m2, d2):
    """
    Tells if the date2 is before bate1
    """
    if (y1 < y2):
        return True
    if (y1 == y2):
        if (m1 < m2):
            return True
        if (m1 == m2):
            return d1 < d2
    return False
    
    

def days_between_dates(y1, m1, d1, y2, m2, d2):
    """
    Calculates the number of days between two dates.
    """
    
    # TODO - by the end of this lesson you will have
    #  completed this function. You do not need to complete
    #  it yet though! 
    assert not dayIsBefore(y2, m2, d2, y1, m1, d1)
    days = 0
    while dayIsBefore(y1, m1, d1, y2, m2, d2):
        y1, m1, d1 = nextDay(y1, m1, d1)
        days += 1
    
    return days

def test():
    """For 30 days in month only"""
    assert days_between_dates(2013,1,1, 2013, 1, 1) == 0
    assert days_between_dates(2013,1,1, 2013, 1, 2) == 1
    assert nextDay(2013,1,1) == (2013,1,2)
    assert nextDay(2013,4,30) == (2013,5,1)
    assert nextDay(2013,2,28) == (2013,3,1)
    assert days_between_dates(2012,1,1, 2013, 1, 1) == 366
    assert days_between_dates(2013,1,1, 2014, 1, 1) == 365
    print('Test finished')  
    
test()

def test_days_between_dates():
    
    # test same day
    assert(days_between_dates(2017, 12, 30,
                              2017, 12, 30) == 0)
    # test adjacent days
    assert(days_between_dates(2017, 12, 30, 
                              2017, 12, 31) == 1)
    # test new year
    assert(days_between_dates(2017, 12, 30, 
                              2018, 1,  1)  == 2)
    # test full year difference
    assert(days_between_dates(2012, 6, 29,
                              2013, 6, 29)  == 365)
    
    print("Congratulations! Your days_between_dates")
    print("function is working correctly!")
    
test_days_between_dates()
