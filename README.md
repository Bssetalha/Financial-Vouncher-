from abc import ABC, abstractmethod

class VoucherConfiguration:
    def __init__(self, name, prefix, suffix, length, voucher_type, format, expiration_date):
        self.name = name
        self.prefix = prefix
        self.suffix = suffix
        self.length = length
        self.voucher_type = voucher_type
        self.format = format
        self.expiration_date = expiration_date

    def update_configuration(self, name=None, prefix=None, suffix=None, length=None, voucher_type=None, format=None, expiration_date=None):
        if name:
            self.name = name
        if prefix:
            self.prefix = prefix
        if suffix:
            self.suffix = suffix
        if length:
            self.length = length
        if voucher_type:
            self.voucher_type = voucher_type
        if format:
            self.format = format
        if expiration_date:
            self.expiration_date = expiration_date

    def delete_configuration(self):
        self.name = None
        self.prefix = None
        self.suffix = None
        self.length = None
        self.voucher_type = None
        self.format = None
        self.expiration_date = None

class Voucher(ABC):
    def __init__(self, voucher_configuration):
        self.voucher_configuration = voucher_configuration

    @abstractmethod
    def generate_voucher(self):
        pass

class AlphanumericVoucher(Voucher):
    def __init__(self, voucher_configuration):
        super().__init__(voucher_configuration)

    def generate_voucher(self):
        # generate alphanumeric voucher based on configuration
        pass

class NumericVoucher(Voucher):
    def __init__(self, voucher_configuration):
        super().__init__(voucher_configuration)

    def generate_voucher(self):
        # generate numeric voucher based on configuration
        pass

class DiscountVoucher(Voucher):
    def __init__(self, voucher_configuration, discount_percentage):
        super().__init__(voucher_configuration)
        self.discount_percentage = discount_percentage

    def generate_voucher(self):
        # generate discount voucher based on configuration and discount percentage
        pass
